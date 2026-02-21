<template>
  <div class="home">

    <!-- ╔══════════════════════════════════════════╗ -->
    <!-- ║  SECTION 1 — Hero "Dreaming in Reels"   ║ -->
    <!-- ╚══════════════════════════════════════════╝ -->
    <section class="section hero-section">
      <!-- Left: image grid placeholder -->
      <div class="hero-grid" aria-label="Portfolio preview grid">
        <div class="grid-main">
          <span class="grid-label">From concept to creation ▶</span>
        </div>
        <div class="grid-quote">
          <p class="grid-quote__text">"Very intelligent<br>and creative"</p>
          <p class="grid-quote__attr">– Industry feedback</p>
        </div>
        <div class="grid-bottom-left">
          <!-- placeholder -->
        </div>
        <div class="grid-bottom-right">
          <span class="grid-label">Connection. Story. Impact.</span>
        </div>
        <!-- Carousel dots -->
        <div class="carousel-dots" aria-hidden="true">
          <span class="dot dot--active" />
          <span class="dot" />
          <span class="dot" />
        </div>
      </div>

      <!-- Right: headline + CTA -->
      <div class="hero-content">
        <div class="stamp stamp--top-right" aria-hidden="true">
          Reels with Rhythm.<br>Content with Heart.
        </div>
        <h1 class="hero-title">Dreaming in Reels</h1>
        <p class="hero-subtitle">Visual storytelling with soul and strategy</p>
        <RouterLink to="/story" class="cta-link">Explore &gt;&gt;&gt;</RouterLink>
      </div>
    </section>

  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
/* ── Page wrapper ─────────────────────────────────────────── */
.home {
  position: relative;
}

/* ── Shared section base ──────────────────────────────────── */
.section {
  min-height: 100vh;
  padding: 5rem 4rem;
  position: relative;
  display: flex;
  align-items: center;
  gap: 4rem;
}

/* ── SECTION 1 — Hero ─────────────────────────────────────── */
.hero-section {
  justify-content: space-between;
}

/* -- Left grid -- */
.hero-grid {
  flex: 0 0 420px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 6px;
  position: relative;
  height: 440px;
}

.grid-main {
  grid-column: 1;
  grid-row: 1;
  background: #c9a882;
  border-radius: 6px;
  position: relative;
  display: flex;
  align-items: flex-end;
  padding: 0.6rem;
}

.grid-quote {
  grid-column: 2;
  grid-row: 1;
  background: rgba(247, 237, 224, 0.9);
  border-radius: 6px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 1rem;
  text-align: center;
}

.grid-quote__text {
  font-family: 'Dancing Script', cursive;
  font-size: 1.35rem;
  color: #5c2a14;
  line-height: 1.3;
}

.grid-quote__attr {
  font-family: 'Lato', sans-serif;
  font-size: 0.75rem;
  color: #7a4028;
  margin-top: 0.4rem;
  font-style: italic;
}

.grid-bottom-left {
  grid-column: 1;
  grid-row: 2;
  background: #b8997a;
  border-radius: 6px;
}

.grid-bottom-right {
  grid-column: 2;
  grid-row: 2;
  background: #c9a882;
  border-radius: 6px;
  display: flex;
  align-items: flex-end;
  padding: 0.6rem;
}

.grid-label {
  font-family: 'Lato', sans-serif;
  font-size: 0.75rem;
  color: #fff;
  background: rgba(0, 0, 0, 0.35);
  padding: 3px 8px;
  border-radius: 4px;
}

.carousel-dots {
  position: absolute;
  bottom: -28px;
  left: 0;
  display: flex;
  gap: 8px;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #c9a882;
  opacity: 0.5;
}

.dot--active {
  background: #b05a3a;
  opacity: 1;
}

/* -- Right hero content -- */
.hero-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  position: relative;
}

.hero-title {
  font-family: 'Dancing Script', cursive;
  font-size: clamp(3rem, 6vw, 5.5rem);
  font-weight: 700;
  color: #5c2a14;
  line-height: 1.1;
  margin-bottom: 0.75rem;
}

.hero-subtitle {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1rem, 2vw, 1.35rem);
  color: #5c2a14;
  margin-bottom: 2rem;
}


/* ── Shared CTA link ─────────────────────────────────────── */
.cta-link {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.2rem;
  font-weight: 700;
  color: #5c2a14;
  text-decoration: underline;
  text-underline-offset: 5px;
  text-decoration-thickness: 2px;
  transition: opacity 0.2s;
}

.cta-link:hover {
  opacity: 0.7;
}

.cta-link--light {
  color: #fff;
  text-decoration-color: rgba(255, 255, 255, 0.6);
  align-self: flex-end;
  font-size: 1.1rem;
}

.cta-link--light:hover {
  opacity: 0.8;
}

/* ── Stamps / tag decorations ────────────────────────────── */
.stamp {
  font-family: 'Lato', sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #7a4028;
  border: 1.5px solid #b08070;
  border-radius: 6px;
  padding: 0.5rem 0.9rem;
  line-height: 1.5;
  text-align: center;
  backdrop-filter: blur(2px);
  background: rgba(247, 237, 224, 0.7);
  pointer-events: none;
  user-select: none;
}

.stamp--top-right {
  position: absolute;
  top: 4rem;
  right: 4rem;
}

.stamp--bottom-center {
  position: absolute;
  bottom: 3rem;
  left: 50%;
  transform: translateX(-50%);
}

.stamp--circle {
  border-radius: 50%;
  width: 110px;
  height: 110px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
  font-size: 0.62rem;
}

/* ── Responsive ──────────────────────────────────────────── */
@media (max-width: 900px) {
  .section {
    padding: 4rem 2rem;
    flex-direction: column;
    min-height: auto;
    gap: 3rem;
  }

  .hero-section {
    padding-bottom: 5rem;
  }

  .hero-grid {
    flex: none;
    width: 100%;
    max-width: 420px;
    height: 320px;
  }

  .hero-content {
    align-items: center;
    text-align: center;
  }

  .stamp--top-right {
    top: 1.5rem;
    right: 1.5rem;
  }

  .stamp--bottom-center {
    bottom: 1.5rem;
  }
}
</style>
