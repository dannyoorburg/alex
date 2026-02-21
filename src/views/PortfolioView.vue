<template>
  <div class="portfolio-page">
    <section class="port-section">

      <!-- Decorative stamp (top-right) -->
      <div class="stamp stamp--tr" aria-hidden="true">
        Reels with Rhythm.<br>Content with Heart.
      </div>

      <!-- Decorative flower + wire (top-right area) -->
      <div class="flower-deco" aria-hidden="true">
        <svg width="60" height="60" viewBox="0 0 60 60" class="flower-icon">
          <circle cx="30" cy="30" r="8" fill="#d4b5a0"/>
          <ellipse cx="30" cy="14" rx="7" ry="10" fill="#e8cfc0" opacity="0.8"/>
          <ellipse cx="30" cy="46" rx="7" ry="10" fill="#e8cfc0" opacity="0.8"/>
          <ellipse cx="14" cy="30" rx="10" ry="7" fill="#e8cfc0" opacity="0.8"/>
          <ellipse cx="46" cy="30" rx="10" ry="7" fill="#e8cfc0" opacity="0.8"/>
          <ellipse cx="19" cy="19" rx="7" ry="10" fill="#e8cfc0" opacity="0.7" transform="rotate(-45 19 19)"/>
          <ellipse cx="41" cy="19" rx="7" ry="10" fill="#e8cfc0" opacity="0.7" transform="rotate(45 41 19)"/>
          <ellipse cx="19" cy="41" rx="7" ry="10" fill="#e8cfc0" opacity="0.7" transform="rotate(45 19 41)"/>
          <ellipse cx="41" cy="41" rx="7" ry="10" fill="#e8cfc0" opacity="0.7" transform="rotate(-45 41 41)"/>
        </svg>
        <svg class="flower-wire" width="140" height="40" viewBox="0 0 140 40">
          <path d="M 0,20 Q 40,5 70,18 Q 100,32 140,15" fill="none" stroke="#c0b5a8" stroke-width="1.2"/>
        </svg>
      </div>

      <!-- Header -->
      <div class="port-header">
        <h1 class="port-title">Portfolio</h1>
        <div class="port-divider"><span class="div-line"/><span class="div-heart">♡</span><span class="div-line"/></div>
      </div>

      <p class="port-subtitle">Selected projects built with rhythm, story, and intent</p>

      <!-- ── Desert Crescendo ─────────────────────────────── -->
      <div class="project project--desert">
        <div class="desert-cover" aria-label="Desert Crescendo magazine cover">
          <div class="cover-inner">
            <span class="cover-top">IL DIVO'S MOST<br>INTIMATE CRESCENDO</span>
            <div class="cover-photo">📷</div>
            <div class="cover-bottom">
              <span class="cover-focus">IN FOCUS: Sébastien Izambard</span>
              <span class="cover-tag">The Voice. The Vulnerability. The Surrender.</span>
            </div>
          </div>
        </div>
        <div class="project-info">
          <h2 class="project-title">Desert Crescendo</h2>
          <p class="project-desc">
            A bold, magazine-style tribute to softness, strength, and Sébastien Izambard.
          </p>
          <RouterLink to="/portfolio/desert-crescendo" class="cta-link cta-link--dark">Step Inside &gt;&gt;&gt;</RouterLink>
        </div>
      </div>

      <!-- ── Sand2Sea ─────────────────────────────────────── -->
      <div class="project project--sea">
        <div class="sea-info">
          <h2 class="project-title">Sand2Sea</h2>
          <p class="project-desc">
            A creative concept for a luxury lifestyle brand focused on calm, clarity, and visual flow.
          </p>
          <RouterLink to="/portfolio/sand2sea" class="cta-link cta-link--dark">Step Inside &nbsp;&gt;&gt;&gt;</RouterLink>
        </div>
        <div class="sea-collage" aria-label="Sand2Sea preview collage">
          <div class="collage-banner">
            <span class="collage-banner-title">Stories from the Shore</span>
            <span class="collage-banner-sub">Moments, Memories &amp; Magic</span>
          </div>
          <div class="collage-cards">
            <div class="collage-card collage-card--1">📷</div>
            <div class="collage-card collage-card--2">📷</div>
            <div class="collage-card collage-card--3">📷</div>
          </div>
        </div>
      </div>

      <!-- Bottom stamp -->
      <div class="stamp stamp--bc" aria-hidden="true">
        Built for Scroll.<br>Made to Stay.
      </div>

    </section>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
/* ── Section ──────────────────────────────────────────────── */
.port-section {
  min-height: 100vh;
  padding: 3rem 5rem 4rem;
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

/* ── Header ───────────────────────────────────────────────── */
.port-header {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.port-title {
  font-family: 'Dancing Script', cursive;
  font-size: clamp(3rem, 7vw, 5.5rem);
  font-weight: 700;
  color: #4a2010;
  line-height: 1.1;
}

.port-divider {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  max-width: 300px;
}

.div-line {
  flex: 1;
  height: 1.5px;
  background: #7a4028;
  border-radius: 2px;
}

.div-heart {
  font-size: 1.1rem;
  color: #7a4028;
  line-height: 1;
}

.port-subtitle {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1rem, 2vw, 1.35rem);
  color: #6b5040;
  margin-top: -0.5rem;
}

/* ── Stamp decorations ────────────────────────────────────── */
.stamp {
  position: absolute;
  font-family: 'Lato', sans-serif;
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.07em;
  text-transform: uppercase;
  color: #7a4028;
  border: 1.5px solid #b08070;
  border-radius: 6px;
  padding: 0.45rem 0.8rem;
  line-height: 1.5;
  text-align: center;
  background: rgba(247, 237, 224, 0.75);
  pointer-events: none;
  user-select: none;
  backdrop-filter: blur(2px);
}

.stamp--tr {
  top: 12rem;
  right: 5rem;
}

.stamp--bc {
  position: relative;
  align-self: center;
  margin-top: 1.5rem;
  border-radius: 50%;
  width: 120px;
  height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.6rem;
  padding: 0;
}

/* ── Flower decoration ────────────────────────────────────── */
.flower-deco {
  position: absolute;
  top: 10rem;
  right: 13rem;
  display: flex;
  align-items: center;
  gap: 0;
  pointer-events: none;
}

.flower-icon {
  display: block;
}

.flower-wire {
  display: block;
  margin-left: -5px;
}

/* ── Project shared ───────────────────────────────────────── */
.project {
  display: flex;
  align-items: center;
  gap: 2.5rem;
  position: relative;
}

.project-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1.4rem, 3vw, 2rem);
  font-weight: 700;
  color: #4a2010;
  line-height: 1.25;
}

.project-desc {
  font-family: 'Lato', sans-serif;
  font-size: 1.05rem;
  color: #5c2a14;
  line-height: 1.7;
  max-width: 360px;
}

.project-info {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  background: rgba(255, 252, 248, 0.8);
  backdrop-filter: blur(4px);
  border-radius: 10px;
  padding: 2rem 2.5rem;
}

.cta-link {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1rem;
  font-weight: 700;
  text-decoration: underline;
  text-underline-offset: 4px;
  text-decoration-thickness: 2px;
  transition: opacity 0.2s;
  align-self: flex-end;
  margin-top: 0.5rem;
}

.cta-link:hover { opacity: 0.65; }

.cta-link--dark {
  color: #4a2010;
  text-decoration-color: rgba(74, 32, 16, 0.45);
}

/* ── Desert Crescendo ─────────────────────────────────────── */
.project--desert {
  margin-top: 1rem;
}

.desert-cover {
  flex: 0 0 260px;
  transform: rotate(-4deg);
  border-radius: 6px;
  overflow: hidden;
  box-shadow: 0 8px 32px rgba(92, 42, 20, 0.22);
}

.cover-inner {
  background: linear-gradient(170deg, #daa520 0%, #c87941 35%, #a0522d 70%, #7a3b1e 100%);
  padding: 1.2rem 1rem;
  display: flex;
  flex-direction: column;
  min-height: 360px;
}

.cover-top {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 0.95rem;
  font-weight: 700;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  line-height: 1.4;
  text-shadow: 0 1px 4px rgba(0,0,0,0.3);
}

.cover-photo {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  opacity: 0.3;
  margin: 0.5rem 0;
}

.cover-bottom {
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
  border-top: 2px solid rgba(255, 255, 255, 0.3);
  padding-top: 0.6rem;
}

.cover-focus {
  font-family: 'Lato', sans-serif;
  font-size: 0.72rem;
  font-weight: 700;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.cover-tag {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 0.7rem;
  font-style: italic;
  color: rgba(255, 255, 255, 0.85);
}

/* ── Sand2Sea ─────────────────────────────────────────────── */
.project--sea {
  margin-left: auto;
  max-width: 850px;
  margin-top: 1rem;
}

.sea-info {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  background: rgba(255, 252, 248, 0.8);
  backdrop-filter: blur(4px);
  border-radius: 10px;
  padding: 2rem 2.5rem;
  flex: 1;
}

.sea-collage {
  flex: 0 0 280px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
  position: relative;
}

.collage-banner {
  background: rgba(247, 240, 232, 0.85);
  border-radius: 6px;
  padding: 0.6rem 1.2rem;
  text-align: center;
  transform: rotate(2deg);
  box-shadow: 0 2px 12px rgba(92, 42, 20, 0.1);
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
}

.collage-banner-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 0.85rem;
  font-weight: 700;
  color: #4a2010;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.collage-banner-sub {
  font-family: 'Dancing Script', cursive;
  font-size: 0.95rem;
  color: #7a4028;
}

.collage-cards {
  display: flex;
  gap: 0.5rem;
  align-items: flex-start;
}

.collage-card {
  width: 75px;
  height: 100px;
  border-radius: 6px;
  background: #d4c5b5;
  box-shadow: 0 3px 12px rgba(92, 42, 20, 0.15);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  opacity: 0.5;
  overflow: hidden;
}

.collage-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.collage-card--1 {
  transform: rotate(-6deg);
  background: #c9b8a5;
}

.collage-card--2 {
  transform: rotate(3deg) translateY(8px);
  background: #d8cfc5;
}

.collage-card--3 {
  transform: rotate(-2deg) translateY(-4px);
  background: #c4b5a5;
}

/* ── Responsive ───────────────────────────────────────────── */
@media (max-width: 900px) {
  .port-section {
    padding: 3rem 2rem 4rem;
  }

  .project {
    flex-direction: column;
    gap: 1.5rem;
  }

  .project--sea {
    margin-left: 0;
    max-width: none;
  }

  .desert-cover {
    flex: none;
    width: 220px;
    transform: rotate(-2deg);
  }

  .sea-collage {
    flex: none;
    width: 100%;
  }

  .stamp--tr {
    top: 1rem;
    right: 1rem;
  }

  .flower-deco {
    top: 1rem;
    right: 7rem;
  }

  .stamp--bc {
    width: 100px;
    height: 100px;
    font-size: 0.55rem;
  }
}
</style>
