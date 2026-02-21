<template>
  <header class="navbar">
    <div class="navbar__inner">

      <!-- Brand / Logo area -->
      <RouterLink to="/" class="navbar__brand">
        <div class="navbar__brand-graphic" aria-hidden="true">
          <!-- Film strip top row -->
          <div class="film-strip">
            <span class="film-perfs">
              <span v-for="n in 7" :key="n" class="perf" />
            </span>
            <span class="film-tagline">
              Social.&nbsp; Strategy.&nbsp; Storytelling.&nbsp; Design.&nbsp; Voice.&nbsp; Impact.
            </span>
            <span class="film-perfs">
              <span v-for="n in 7" :key="n" class="perf" />
            </span>
          </div>
          <!-- Scissors -->
          <span class="scissors" aria-hidden="true">✂</span>
        </div>
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
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

interface NavLink {
  label: string
  to: string
}

const navLinks: NavLink[] = [
  { label: 'About Me', to: '/about' },
  { label: 'Portfolio', to: '/portfolio' },
  { label: 'Services', to: '/services' },
  { label: 'Contact', to: '/contact' },
]

const menuOpen = ref<boolean>(false)
</script>

<style scoped>
/* ── Variables ───────────────────────────────────────────── */
.navbar {
  --color-brown: #5c2a14;
  --color-brown-light: #7a4028;
  --color-bg: #f7ede0;
  --color-bg-glass: rgba(247, 237, 224, 0.92);
  --font-serif: 'Playfair Display', Georgia, serif;
  --font-body: 'Lato', system-ui, sans-serif;

  position: sticky;
  top: 0;
  z-index: 200;
  background: var(--color-bg-glass);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(92, 42, 20, 0.12);
}

/* ── Inner layout ────────────────────────────────────────── */
.navbar__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0.5rem 2rem;
  gap: 1.5rem;
}

/* ── Brand / film strip ──────────────────────────────────── */
.navbar__brand {
  text-decoration: none;
  flex-shrink: 0;
}

.navbar__brand-graphic {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 2px;
}

.film-strip {
  display: flex;
  flex-direction: column;
  gap: 2px;
  font-family: var(--font-body);
  font-size: 0.68rem;
  letter-spacing: 0.05em;
  color: var(--color-brown);
  border: 2px solid var(--color-brown);
  border-radius: 4px;
  padding: 0;
  overflow: hidden;
  min-width: 260px;
}

.film-perfs {
  display: flex;
  background: var(--color-brown);
  padding: 1px 4px;
  gap: 6px;
  flex-wrap: nowrap;
}

.perf {
  display: inline-block;
  width: 12px;
  height: 8px;
  background: var(--color-bg);
  border-radius: 2px;
  flex-shrink: 0;
}

.film-tagline {
  display: block;
  padding: 4px 6px;
  color: var(--color-brown);
  font-weight: 700;
  font-size: 0.65rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.scissors {
  position: absolute;
  right: -14px;
  top: 50%;
  transform: translateY(-50%) rotate(45deg);
  font-size: 1.1rem;
  color: var(--color-brown);
  opacity: 0.7;
}

/* ── Desktop nav links ───────────────────────────────────── */
.navbar__nav {
  display: flex;
  align-items: center;
  gap: 2.5rem;
}

.navbar__link {
  font-family: var(--font-serif);
  font-size: 1rem;
  font-weight: 400;
  color: var(--color-brown);
  text-decoration: underline;
  text-underline-offset: 4px;
  text-decoration-thickness: 1.5px;
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
  width: 32px;
  height: 32px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  flex-shrink: 0;
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
  background: var(--color-bg);
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

/* ── Hide desktop nav on mobile, show hamburger inline ───── */
@media (max-width: 768px) {
  .navbar__nav {
    display: none;
  }

  .navbar__hamburger {
    display: flex;
  }
}

@media (min-width: 769px) {
  .navbar__hamburger {
    /* Keep hamburger always visible to match the design reference */
    display: flex;
  }

  .navbar__mobile-menu {
    display: none !important;
  }
}
</style>
