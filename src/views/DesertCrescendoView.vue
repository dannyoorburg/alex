<template>
  <div class="dc-page">

    <RouterLink to="/portfolio" class="back-link">Back to Portfolio &gt;&gt;&gt;</RouterLink>

    <div class="dc-content">
      <!-- Left: title block -->
      <div class="dc-left">
        <p class="dc-sub">A tribute to strength, softness...<br>and the silence between notes</p>
      </div>

      <!-- Right: magazine mockups -->
      <div class="dc-mockups">
        <div class="magazine magazine--back">
          <p class="mag-label">IL DIVO'S MOST INTIMATE CRESCENDO</p>
          <p class="mag-tag">IN FOCUS: Sébastien Izambard<br><span>The Voice. The Vulnerability. The Surrender.</span></p>
        </div>
        <div class="magazine magazine--front">
          <p class="mag-title-big">SOLACE</p>
          <p class="mag-sub-small">Softness. With Intent.</p>
        </div>
      </div>
    </div>

    <!-- Bottom description bar -->
    <div class="dc-description">
      <p>A creative reflection on Il Divo's Sébastien Izambard. Featuring curated imagery and custom edits, this project blends magazine-style design with cinematic rhythm and emotional narrative.</p>
    </div>

  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
.dc-page {
  min-height: 100vh;
  background:
    linear-gradient(
      to bottom,
      rgba(30, 15, 5, 0.45) 0%,
      rgba(20, 10, 2, 0.2) 40%,
      rgba(20, 10, 2, 0.55) 80%,
      rgba(10, 5, 0, 0.75) 100%
    ),
    linear-gradient(
      160deg,
      #d4883a 0%,
      #c07030 20%,
      #a05828 40%,
      #884020 60%,
      #6a2e14 80%,
      #4a1e08 100%
    );
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
}

/* sand dune texture via subtle noise overlay */
.dc-page::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    repeating-linear-gradient(
      80deg,
      rgba(255,200,100,0.04) 0px,
      rgba(255,200,100,0.04) 1px,
      transparent 1px,
      transparent 60px
    ),
    repeating-linear-gradient(
      170deg,
      rgba(180,100,30,0.05) 0px,
      rgba(180,100,30,0.05) 1px,
      transparent 1px,
      transparent 40px
    );
  pointer-events: none;
}

/* ── Back link ── */
.back-link {
  position: absolute;
  top: 2.5rem;
  right: 3.5rem;
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1rem;
  font-weight: 700;
  color: rgba(255,255,255,0.9);
  text-decoration: underline;
  text-underline-offset: 4px;
  text-decoration-thickness: 1.5px;
  transition: opacity 0.2s;
  z-index: 2;
}
.back-link:hover { opacity: 0.7; }

/* ── Main content ── */
.dc-content {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 6rem 5rem 3rem;
  gap: 3rem;
  position: relative;
  z-index: 1;
}

/* ── Left: title ── */
.dc-left {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  max-width: 560px;
}

.dc-title {
  font-family: 'Lato', sans-serif;
  font-size: clamp(4rem, 9vw, 8rem);
  font-weight: 900;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #fff;
  line-height: 0.95;
  text-shadow:
    3px 3px 0 rgba(0,0,0,0.4),
    -1px -1px 0 rgba(0,0,0,0.2),
    0 0 40px rgba(220,140,60,0.3);
  /* distressed / stamp feel */
  -webkit-text-stroke: 1px rgba(255,255,255,0.15);
}

.dc-rule {
  width: 200px;
  height: 1.5px;
  background: rgba(255,255,255,0.5);
  border-radius: 2px;
}

.dc-sub {
  font-family: 'Lato', sans-serif;
  font-size: clamp(0.85rem, 1.5vw, 1.05rem);
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: rgba(255,255,255,0.85);
  line-height: 1.6;
}

/* ── Right: magazines ── */
.dc-mockups {
  position: relative;
  width: 360px;
  height: 380px;
  flex-shrink: 0;
}

.magazine {
  position: absolute;
  border-radius: 6px;
  overflow: hidden;
  box-shadow: 0 8px 40px rgba(0,0,0,0.5);
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 1rem;
}

.magazine--back {
  width: 200px;
  height: 280px;
  top: 20px;
  right: 0;
  transform: rotate(4deg);
  background: linear-gradient(175deg, #c87941 0%, #8a4820 50%, #5a2c10 100%);
}

.magazine--front {
  width: 180px;
  height: 250px;
  top: 80px;
  right: 140px;
  transform: rotate(-5deg);
  background: linear-gradient(175deg, #b06030 0%, #703820 50%, #401808 100%);
  justify-content: center;
  align-items: flex-start;
}

.mag-label {
  font-family: 'Lato', sans-serif;
  font-size: 0.65rem;
  font-weight: 900;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #fff;
  line-height: 1.3;
  margin-bottom: 0.5rem;
}

.mag-tag {
  font-family: 'Lato', sans-serif;
  font-size: 0.62rem;
  font-weight: 700;
  color: rgba(255,255,255,0.85);
  background: rgba(0,0,0,0.4);
  padding: 4px 8px;
  border-radius: 3px;
  line-height: 1.5;
}

.mag-tag span {
  font-weight: 400;
  font-style: italic;
  display: block;
}

.mag-title-big {
  font-family: 'Lato', sans-serif;
  font-size: 2.8rem;
  font-weight: 900;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #fff;
  line-height: 1;
  text-shadow: 2px 2px 8px rgba(0,0,0,0.4);
  padding: 0 1rem;
}

.mag-sub-small {
  font-family: 'Lato', sans-serif;
  font-size: 0.72rem;
  letter-spacing: 0.12em;
  color: rgba(255,255,255,0.8);
  font-style: italic;
  padding: 0 1rem;
  margin-top: 0.4rem;
}

/* ── Bottom description ── */
.dc-description {
  background: rgba(0,0,0,0.45);
  backdrop-filter: blur(6px);
  padding: 1.75rem 5rem;
  position: relative;
  z-index: 1;
}

.dc-description p {
  font-family: 'Lato', sans-serif;
  font-size: 1rem;
  color: rgba(255,255,255,0.9);
  line-height: 1.7;
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
}

/* ── Responsive ── */
@media (max-width: 900px) {
  .dc-content {
    flex-direction: column;
    padding: 5rem 2rem 2rem;
    align-items: flex-start;
  }
  .dc-mockups { width: 100%; height: 280px; }
  .dc-description { padding: 1.5rem 2rem; }
  .back-link { top: 1.5rem; right: 1.5rem; }
}
</style>
