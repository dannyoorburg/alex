<template>
  <div class="s2s-page">
    <section class="s2s-section">

      <div class="s2s-header">
        <div class="s2s-title-col">
          <p class="s2s-tagline">Where calm meets clarity — a digital presence designed to breathe.</p>
        </div>
      </div>

      <div class="s2s-body">
        <!-- Left: stacked mockup images -->
        <div class="s2s-images">
          <div class="mockup mockup--back">
            <div class="mockup-inner">
              <p class="mockup-title">STORIES FROM THE SHORE</p>
              <p class="mockup-sub">Moments. Memories &amp; Magic</p>
              <div class="mockup-photos">
                <div class="photo-chip">Sip. Float. Repeat</div>
                <div class="photo-chip">Floating to Coming Home</div>
                <div class="photo-chip">Feel Beyond the Bend</div>
              </div>
            </div>
          </div>
          <div class="mockup mockup--front">
            <div class="mockup-inner mockup-inner--breathe">
              <p class="mockup-script">Breathe<strong>Easy</strong></p>
              <p class="mockup-detail">The S2S is a premium 2-in-1 tote and lounger designed to help you pause, float and exhale.</p>
              <p class="mockup-italic">float into stillness</p>
            </div>
          </div>
        </div>

        <!-- Right: rose paper card -->
        <div class="s2s-card">
          <p>A self-led concept created for a luxury lifestyle brand, blending warmth, elegance, and visual stillness. This homepage design invites visitors into a premium brand experience from the very first scroll — calm, coastal, and curated with care.</p>
          <ul>
            <li>Custom layout &amp; navigation flow</li>
            <li>Brand tone and visual identity matching</li>
            <li>Copywriting &amp; creative direction</li>
          </ul>
        </div>
      </div>

      <div class="s2s-footer">
        <RouterLink to="/portfolio" class="back-link">Back to Portfolio &gt;&gt;&gt;</RouterLink>
      </div>

    </section>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
.s2s-page {
  min-height: 100vh;
}

.s2s-section {
  min-height: 100vh;
  padding: 4rem 5rem 5rem;
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

/* ── Header ── */
.s2s-header {
  display: flex;
  align-items: flex-end;
  gap: 3rem;
}

.s2s-title {
  font-family: 'Dancing Script', cursive;
  font-size: clamp(3rem, 7vw, 5.5rem);
  font-weight: 700;
  color: #4a2010;
  line-height: 1.1;
}

.s2s-divider {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  max-width: 260px;
  margin-top: 0.25rem;
}

.div-line {
  flex: 1;
  height: 1.5px;
  background: #7a4028;
  border-radius: 2px;
  display: block;
}

.div-heart {
  font-size: 1.1rem;
  color: #7a4028;
  line-height: 1;
}

.s2s-tagline {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1.1rem, 2.2vw, 1.5rem);
  color: #5c2a14;
  margin-top: 0.75rem;
  max-width: 600px;
  line-height: 1.5;
}

/* ── Body ── */
.s2s-body {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

/* ── Mockup images ── */
.s2s-images {
  position: relative;
  height: 380px;
}

.mockup {
  position: absolute;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 6px 24px rgba(92,42,20,0.18);
}

.mockup--back {
  width: 260px;
  height: 300px;
  top: 40px;
  left: 120px;
  transform: rotate(3deg);
  background: linear-gradient(135deg, #d4c5b5 0%, #c8b8a8 100%);
}

.mockup--front {
  width: 240px;
  height: 280px;
  top: 10px;
  left: 0;
  transform: rotate(-4deg);
  background: linear-gradient(135deg, #b8d4d8 0%, #8ab0b8 60%, #5a8898 100%);
}

.mockup-inner {
  padding: 1.2rem;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.mockup-title {
  font-family: 'Lato', sans-serif;
  font-size: 0.72rem;
  font-weight: 900;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #3a2010;
}

.mockup-sub {
  font-family: 'Dancing Script', cursive;
  font-size: 0.95rem;
  color: #5c3820;
}

.mockup-photos {
  display: flex;
  gap: 0.35rem;
  margin-top: auto;
  flex-wrap: wrap;
}

.photo-chip {
  background: rgba(255,255,255,0.6);
  border-radius: 3px;
  padding: 2px 5px;
  font-family: 'Lato', sans-serif;
  font-size: 0.6rem;
  color: #4a2010;
}

.mockup-inner--breathe {
  justify-content: flex-end;
  background: rgba(255,255,255,0.1);
}

.mockup-script {
  font-family: 'Lato', sans-serif;
  font-size: 1.1rem;
  color: #fff;
  font-style: italic;
}

.mockup-script strong {
  font-weight: 900;
  font-style: normal;
}

.mockup-detail {
  font-family: 'Lato', sans-serif;
  font-size: 0.68rem;
  color: rgba(255,255,255,0.9);
  line-height: 1.4;
}

.mockup-italic {
  font-family: 'Dancing Script', cursive;
  font-size: 0.95rem;
  color: rgba(255,255,255,0.8);
  margin-top: 0.25rem;
}

/* ── Rose card ── */
.s2s-card {
  background: #e8c8be;
  border-radius: 2px 30px 2px 30px;
  padding: 2.5rem 3rem;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  /* torn paper feel */
  clip-path: polygon(
    0% 2%, 3% 0%, 97% 1%, 100% 0%,
    100% 98%, 97% 100%, 4% 99%, 0% 100%
  );
}

.s2s-card p {
  font-family: 'Dancing Script', cursive;
  font-size: 1.15rem;
  color: #4a2010;
  line-height: 1.8;
}

.s2s-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}

.s2s-card li {
  font-family: 'Dancing Script', cursive;
  font-size: 1.05rem;
  color: #4a2010;
  padding-left: 1rem;
  position: relative;
}

.s2s-card li::before {
  content: '–';
  position: absolute;
  left: 0;
}

/* ── Footer ── */
.s2s-footer {
  display: flex;
  justify-content: flex-end;
}

.back-link {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.1rem;
  font-weight: 700;
  color: #5c2a14;
  text-decoration: underline;
  text-underline-offset: 5px;
  text-decoration-thickness: 2px;
  transition: opacity 0.2s;
}

.back-link:hover { opacity: 0.65; }

/* ── Responsive ── */
@media (max-width: 900px) {
  .s2s-section { padding: 3rem 2rem 4rem; gap: 2rem; }
  .s2s-body { grid-template-columns: 1fr; }
  .s2s-images { height: 300px; }
}
</style>
