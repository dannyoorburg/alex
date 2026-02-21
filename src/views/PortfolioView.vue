<template>
  <div class="portfolio-page">
    <section class="pg-section">
      <div class="stamp stamp--top-right" aria-hidden="true">Reels with Rhythm.<br>Content with Heart.</div>

      <div class="pg-header">
        <h1 class="pg-title">Portfolio</h1>
        <div class="pg-divider"><span class="div-line"/><span class="div-heart">?</span><span class="div-line"/></div>
      </div>

      <p class="pg-subtitle">Selected projects built with rhythm, story, and intent</p>

      <div class="projects">

        <!-- Desert Crescendo -->
        <div class="project-card">
          <div class="project-thumb project-thumb--desert" aria-label="Desert Crescendo preview">
            <span class="thumb-label">IL DIVO'S MOST INTIMATE CRESCENDO</span>
          </div>
          <div class="project-info">
            <h2 class="project-title">Desert Crescendo</h2>
            <p class="project-desc">A bold, magazine-style tribute to softness, strength, and S�bastien Izambard.</p>
            <RouterLink to="/portfolio/desert-crescendo" class="cta-link">Step Inside &gt;&gt;&gt;</RouterLink>
          </div>
        </div>

        <!-- Sand2Sea -->
        <div class="project-card project-card--reverse">
          <div class="project-info">
            <h2 class="project-title">Sand2Sea</h2>
            <p class="project-desc">A creative concept for a luxury lifestyle brand focused on calm, clarity, and visual flow.</p>
            <RouterLink to="/portfolio/sand2sea" class="cta-link">Step Inside &gt;&gt;&gt;</RouterLink>
          </div>
          <div class="project-thumb project-thumb--sea" aria-label="Sand2Sea preview">
            <div class="thumb-cards">
              <div class="thumb-mini">Stories from the Shore</div>
              <div class="thumb-mini thumb-mini--alt">Moments. Memories &amp; Magic</div>
            </div>
          </div>
        </div>

      </div>

    </section>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
@import '@/assets/page.css';

.projects {
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
  width: 100%;
  max-width: 1100px;
}

.project-card {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 0;
  align-items: stretch;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 24px rgba(92,42,20,0.12);
}

.project-card--reverse {
  grid-template-columns: 1fr 280px;
}

.project-thumb {
  position: relative;
  min-height: 220px;
  display: flex;
  align-items: flex-end;
  padding: 1rem;
}

.project-thumb--desert {
  background: linear-gradient(160deg, #c87941 0%, #a0522d 40%, #7a3b1e 100%);
}

.project-thumb--sea {
  background: linear-gradient(160deg, #d4c5b5 0%, #c4b5a5 50%, #b8a898 100%);
  align-items: center;
  justify-content: center;
}

.thumb-label {
  font-family: 'Lato', sans-serif;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #fff;
  background: rgba(0,0,0,0.35);
  padding: 4px 8px;
  border-radius: 4px;
}

.thumb-cards {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  align-items: center;
}

.thumb-mini {
  background: rgba(255,255,255,0.7);
  border-radius: 4px;
  padding: 0.4rem 0.8rem;
  font-family: 'Lato', sans-serif;
  font-size: 0.7rem;
  color: #5c2a14;
  font-weight: 700;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

.thumb-mini--alt {
  background: rgba(255,255,255,0.5);
  font-style: italic;
  text-transform: none;
  letter-spacing: 0;
}

.project-info {
  background: rgba(255,255,255,0.75);
  backdrop-filter: blur(4px);
  padding: 2.5rem 2.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 0.75rem;
}

.project-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1.5rem, 3vw, 2.2rem);
  font-weight: 700;
  color: #4a2010;
  line-height: 1.2;
}

.project-desc {
  font-family: 'Lato', sans-serif;
  font-size: 1.05rem;
  color: #5c2a14;
  line-height: 1.65;
  max-width: 480px;
}

.cta-link {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.1rem;
  font-weight: 700;
  color: #5c2a14;
  text-decoration: underline;
  text-underline-offset: 5px;
  text-decoration-thickness: 2px;
  transition: opacity 0.2s;
  align-self: flex-start;
}
.cta-link:hover { opacity: 0.65; }

.stamp--bottom-center {
  position: relative;
  align-self: center;
  margin-top: 1rem;
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

@media (max-width: 700px) {
  .project-card,
  .project-card--reverse {
    grid-template-columns: 1fr;
  }
  .project-thumb { min-height: 160px; }
  .project-info { padding: 1.5rem; }
}
</style>
