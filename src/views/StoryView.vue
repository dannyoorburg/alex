<template>
  <div class="story-page">
    <section class="section story-section">
      <div class="stamp stamp--top-right" aria-hidden="true">
        Reels with Rhythm.<br>Content with Heart.
      </div>

      <h2 class="story-title">
        <span class="story-heart" aria-hidden="true">♡</span>
        Rooted in story. Powered by soul.
        <span class="story-quill" aria-hidden="true">✒</span>
      </h2>

      <div class="story-card">
        <p>Where visual storytelling is crafted with purpose, rhythm, and heart.</p>
        <p>We craft content that connects. Reels that resonate. Stories that stay long after the scroll.</p>
        <p>For brands with vision and creators with heart, Dreaming in Reels delivers content that moves, engages, and brings your message to life — with soul and strategy.</p>
        <RouterLink to="/about" class="cta-link cta-link--light">About Me &gt;&gt;&gt;</RouterLink>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
.story-page {
  position: relative;
}

.section {
  min-height: 100vh;
  padding: 5rem 4rem;
  position: relative;
  display: flex;
  align-items: center;
  gap: 4rem;
}

.story-section {
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding-top: 4rem;
  padding-bottom: 6rem;
}

.story-title {
  font-family: 'Dancing Script', cursive;
  font-size: clamp(2.8rem, 5.5vw, 5rem);
  font-weight: 700;
  color: #4a2010;
  line-height: 1.15;
  margin-bottom: 2.5rem;
  max-width: 900px;
  position: relative;
}

.story-heart {
  font-size: 0.6em;
  vertical-align: super;
  margin-right: 0.15em;
  color: #7a4028;
}

.story-quill {
  font-size: 0.7em;
  margin-left: 0.3em;
  display: inline-block;
  transform: rotate(-20deg);
  color: #5c2a14;
  opacity: 0.75;
}

.story-card {
  background: #c07a6a;
  border-radius: 0 40px 0 40px;
  padding: 2.5rem 3rem;
  max-width: 900px;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.story-card p {
  font-family: 'Lato', sans-serif;
  font-size: 1.1rem;
  color: #fff;
  line-height: 1.7;
}

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

@media (max-width: 900px) {
  .section {
    padding: 4rem 2rem;
    flex-direction: column;
    min-height: auto;
    gap: 3rem;
  }

  .stamp--top-right {
    top: 1.5rem;
    right: 1.5rem;
  }

  .story-section {
    padding-top: 3rem;
    padding-bottom: 4rem;
  }

  .story-card {
    padding: 2rem;
  }
}
</style>
