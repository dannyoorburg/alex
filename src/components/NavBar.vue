<template>
  <header class="navbar">
    <div class="navbar__inner">

      <!-- Brand / Film-strip SVG -->
      <RouterLink to="/" class="navbar__brand" aria-label="Home">
        <svg
          class="film-svg"
          viewBox="-25 -20 640 165"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          preserveAspectRatio="xMinYMid meet"
        >
          <defs>
            <!-- Text follows a path below the strip -->
            <path id="textCurve"
              d="M 5,28 C 90,8 205,123 325,123 C 435,122 520,53 595,63" />
          </defs>

          <!-- ── Film-strip body ──────────────────────────── -->
          <path
            :d="stripBodyPath"
            fill="#8a8580" opacity="0.8"
          />

          <!-- ── Frame divider lines inside strip ─────────── -->
          <line
            v-for="(f, i) in frames"
            :key="'f' + i"
            :x1="f.tx" :y1="f.ty"
            :x2="f.bx" :y2="f.by"
            stroke="#6b6560" stroke-width="0.8" opacity="0.3"
          />

          <!-- ── Top edge perforations ────────────────────── -->
          <rect
            v-for="(p, i) in topPerfs"
            :key="'tp' + i"
            :x="p.x - 5.5" :y="p.y - 3"
            width="11" height="6" rx="1.5"
            :transform="`rotate(${p.angle} ${p.x} ${p.y})`"
            fill="#ede7df"
          />

          <!-- ── Bottom edge perforations ─────────────────── -->
          <rect
            v-for="(p, i) in botPerfs"
            :key="'bp' + i"
            :x="p.x - 5.5" :y="p.y - 3"
            width="11" height="6" rx="1.5"
            :transform="`rotate(${p.angle} ${p.x} ${p.y})`"
            fill="#ede7df"
          />

          <!-- ── Tagline text on curved path ──────────────── -->
          <text
            font-family="'Lato', sans-serif"
            font-size="14"
            font-weight="700"
            letter-spacing="1.5"
            fill="#8a8580"
          >
            <textPath href="#textCurve" startOffset="1%">
              Social.&#160;&#160;Strategy.&#160;&#160;Storytelling.&#160;&#160;Design.&#160;&#160;Voice.&#160;&#160;Impact.
            </textPath>
          </text>

          <!-- ── Scissors at end of strip ─────────────────── -->
          <g :transform="`translate(${scissorPos.x} ${scissorPos.y}) rotate(${scissorPos.angle})`">
            <!-- Top blade -->
            <ellipse cx="-10" cy="-3" rx="13" ry="3.5"
              fill="none" stroke="#8a8580" stroke-width="2" />
            <!-- Bottom blade -->
            <ellipse cx="-10" cy="3" rx="13" ry="3.5"
              fill="none" stroke="#8a8580" stroke-width="2" />
            <!-- Top handle loop -->
            <circle cx="7" cy="-7" r="5"
              fill="none" stroke="#8a8580" stroke-width="1.8" />
            <!-- Bottom handle loop -->
            <circle cx="7" cy="7" r="5"
              fill="none" stroke="#8a8580" stroke-width="1.8" />
            <!-- Pivot screw -->
            <circle cx="0" cy="0" r="1.8" fill="#8a8580" />
          </g>

          <!-- ── Subtle brush-stroke deco (right side) ────── -->
          <path
            d="M 450,-12 Q 480,-14 530,-10 Q 560,-8 580,-12"
            fill="none" stroke="#c0b5a8" stroke-width="3"
            stroke-linecap="round" opacity="0.35"
          />
        </svg>
      </RouterLink>

      <!-- Desktop nav -->
      <nav class="navbar__nav" :class="{ 'navbar__nav--open': menuOpen }" aria-label="Main navigation">
        <RouterLink
          v-for="link in navLinks"
          :key="link.to"
          :to="link.to"
          class="navbar__link"
          @click="menuOpen = false"
        >
          {{ link.label }}
        </RouterLink>
      </nav>

      <!-- Hamburger -->
      <button
        class="navbar__hamburger"
        :aria-expanded="menuOpen"
        aria-label="Toggle navigation"
        @click="menuOpen = !menuOpen"
      >
        <span class="bar" />
        <span class="bar" />
        <span class="bar" />
      </button>

    </div>

    <!-- Mobile dropdown -->
    <Transition name="slide-down">
      <nav
        v-if="menuOpen"
        class="navbar__mobile-menu"
        aria-label="Mobile navigation"
      >
        <RouterLink
          v-for="link in navLinks"
          :key="link.to"
          :to="link.to"
          class="navbar__mobile-link"
          @click="menuOpen = false"
        >
          {{ link.label }}
        </RouterLink>
      </nav>
    </Transition>
  </header>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { RouterLink } from 'vue-router'

/* ── Nav links ──────────────────────────────────────────── */
interface NavLink { label: string; to: string }

const navLinks: NavLink[] = [
  { label: 'About Me', to: '/about' },
  { label: 'Portfolio', to: '/portfolio' },
  { label: 'Services', to: '/services' },
  { label: 'Contact', to: '/contact' },
]

const menuOpen = ref(false)

/* ── Bezier helpers ─────────────────────────────────────── */
function bez(t: number, a: number, b: number, c: number, d: number) {
  const s = 1 - t
  return s * s * s * a + 3 * s * s * t * b + 3 * s * t * t * c + t * t * t * d
}

function bezD(t: number, a: number, b: number, c: number, d: number) {
  const s = 1 - t
  return 3 * s * s * (b - a) + 6 * s * t * (c - b) + 3 * t * t * (d - c)
}

/* ── Film-strip center-line definition ──────────────────── */
// Two cubic-bezier segments forming the S-curve
const segs = [
  { x: [-20, 70, 190, 310] as const, y: [-8, -25, 88, 88] as const },
  { x: [310, 420, 510, 580] as const, y: [88, 88, 18, 28] as const },
]

const HALF = 15          // half strip width (total = 30 px)
const PERF_INSET = 4     // how far inside the edge perforations sit
const PERFS_PER_SEG = 12 // perforations per bezier segment per edge

/* ── Sample a point on the center curve ─────────────────── */
interface Pt { x: number; y: number; angle: number }

function sample(segIdx: number, t: number, offset: number): Pt {
  const s = segs[segIdx]
  const cx = bez(t, s.x[0], s.x[1], s.x[2], s.x[3])
  const cy = bez(t, s.y[0], s.y[1], s.y[2], s.y[3])
  const dx = bezD(t, s.x[0], s.x[1], s.x[2], s.x[3])
  const dy = bezD(t, s.y[0], s.y[1], s.y[2], s.y[3])
  const len = Math.sqrt(dx * dx + dy * dy) || 1
  // Normal pointing to "top" of strip (outward from concave side)
  const nx = dy / len
  const ny = -dx / len
  const angle = Math.atan2(dy, dx) * (180 / Math.PI)
  return {
    x: +(cx + nx * offset).toFixed(1),
    y: +(cy + ny * offset).toFixed(1),
    angle: +angle.toFixed(1),
  }
}

/* ── Perforation positions ──────────────────────────────── */
function buildPerfs(offset: number): Pt[] {
  const pts: Pt[] = []
  for (let s = 0; s < segs.length; s++) {
    const from = s === 0 ? 0 : 1
    for (let i = from; i <= PERFS_PER_SEG; i++) {
      pts.push(sample(s, i / PERFS_PER_SEG, offset))
    }
  }
  return pts
}

const topPerfs = computed(() => buildPerfs(HALF - PERF_INSET))
const botPerfs = computed(() => buildPerfs(-(HALF - PERF_INSET)))

/* ── Frame divider lines across the strip ───────────────── */
const frames = computed(() => {
  const lines: { tx: number; ty: number; bx: number; by: number }[] = []
  const perSeg = 8
  for (let s = 0; s < segs.length; s++) {
    for (let i = 1; i < perSeg; i++) {
      const top = sample(s, i / perSeg, HALF - 1)
      const bot = sample(s, i / perSeg, -(HALF - 1))
      lines.push({ tx: top.x, ty: top.y, bx: bot.x, by: bot.y })
    }
  }
  return lines
})

/* ── Strip body SVG path (top edge forward → bottom edge reverse) */
const stripBodyPath = computed(() => {
  const H = HALF
  const s1 = segs[0]; const s2 = segs[1]
  // Approximate offset by shifting y values ± HALF
  return [
    `M ${s1.x[0]},${s1.y[0] - H}`,
    `C ${s1.x[1]},${s1.y[1] - H} ${s1.x[2]},${s1.y[2] - H} ${s1.x[3]},${s1.y[3] - H}`,
    `C ${s2.x[1]},${s2.y[1] - H} ${s2.x[2]},${s2.y[2] - H} ${s2.x[3]},${s2.y[3] - H}`,
    `L ${s2.x[3]},${s2.y[3] + H}`,
    `C ${s2.x[2]},${s2.y[2] + H} ${s2.x[1]},${s2.y[1] + H} ${s2.x[0]},${s2.y[0] + H}`,
    `C ${s1.x[2]},${s1.y[2] + H} ${s1.x[1]},${s1.y[1] + H} ${s1.x[0]},${s1.y[0] + H}`,
    'Z',
  ].join(' ')
})

/* ── Scissors position at the strip end ─────────────────── */
const scissorPos = computed(() => {
  const s = segs[1]
  const t = 1
  const dx = bezD(t, s.x[0], s.x[1], s.x[2], s.x[3])
  const dy = bezD(t, s.y[0], s.y[1], s.y[2], s.y[3])
  const angle = Math.atan2(dy, dx) * (180 / Math.PI)
  return {
    x: +(s.x[3] + 22).toFixed(0),
    y: +(s.y[3] + 5).toFixed(0),
    angle: +angle.toFixed(0),
  }
})
</script>

<style scoped>
/* ── Variables ───────────────────────────────────────────── */
.navbar {
  --color-brown: #5c2a14;
  --color-brown-light: #7a4028;
  --font-serif: 'Playfair Display', Georgia, serif;
  --font-body: 'Lato', system-ui, sans-serif;

  position: sticky;
  top: 0;
  z-index: 200;
  background: transparent;
  border-bottom: none;
}

/* ── Inner layout ────────────────────────────────────────── */
.navbar__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0;
  gap: 1rem;
}

/* ── Brand / Film-strip SVG ──────────────────────────────── */
.navbar__brand {
  text-decoration: none;
  flex-shrink: 1;
  min-width: 0;
  flex: 0 1 520px;
  margin-left: -0.5rem;
}

.film-svg {
  display: block;
  width: 100%;
  height: auto;
  max-height: 130px;
  overflow: visible;
}

/* ── Desktop nav links ───────────────────────────────────── */
.navbar__nav {
  display: flex;
  align-items: center;
  gap: 2.5rem;
  padding-right: 0.5rem;
}

.navbar__link {
  font-family: var(--font-serif);
  font-size: 1.05rem;
  font-weight: 400;
  color: var(--color-brown);
  text-decoration: underline;
  text-underline-offset: 5px;
  text-decoration-thickness: 1.5px;
  text-decoration-color: var(--color-brown);
  transition: color 0.2s, text-decoration-color 0.2s;
  white-space: nowrap;
}

.navbar__link:hover,
.navbar__link.router-link-active {
  color: var(--color-brown-light);
  font-weight: 600;
}

/* ── Hamburger ───────────────────────────────────────────── */
.navbar__hamburger {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 30px;
  height: 30px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  flex-shrink: 0;
  margin-right: 1.5rem;
}

.bar {
  display: block;
  width: 100%;
  height: 2.5px;
  background: var(--color-brown);
  border-radius: 2px;
  transition: all 0.25s;
}

/* ── Mobile dropdown ─────────────────────────────────────── */
.navbar__mobile-menu {
  display: flex;
  flex-direction: column;
  background: rgba(237, 231, 223, 0.95);
  backdrop-filter: blur(8px);
  border-top: 1px solid rgba(92, 42, 20, 0.1);
  padding: 1rem 2rem 1.5rem;
  gap: 0.25rem;
}

.navbar__mobile-link {
  font-family: var(--font-serif);
  font-size: 1.15rem;
  color: var(--color-brown);
  text-decoration: none;
  padding: 0.6rem 0;
  border-bottom: 1px solid rgba(92, 42, 20, 0.1);
  transition: color 0.2s;
}

.navbar__mobile-link:hover,
.navbar__mobile-link.router-link-active {
  color: var(--color-brown-light);
  font-weight: 600;
}

/* ── Transition ──────────────────────────────────────────── */
.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.25s ease;
  overflow: hidden;
}

.slide-down-enter-from,
.slide-down-leave-to {
  max-height: 0;
  opacity: 0;
}

.slide-down-enter-to,
.slide-down-leave-from {
  max-height: 300px;
  opacity: 1;
}

/* ── Responsive ──────────────────────────────────────────── */
@media (max-width: 768px) {
  .navbar__nav {
    display: none;
  }

  .navbar__brand {
    flex: 0 1 320px;
  }

  .navbar__hamburger {
    display: flex;
    margin-right: 1rem;
  }
}

@media (min-width: 769px) {
  .navbar__hamburger {
    display: flex;
  }

  .navbar__mobile-menu {
    display: none !important;
  }
}
</style>
