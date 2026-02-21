<template>
  <div class="about">
    <section class="pg-section">

      <div class="two-col">
        <div class="card card--salmon">
          <p>I'm Alex — a journalist-turned-content strategist with a career spent chasing the heart of the story.</p>
          <p>Now, I help brands and creatives show up with clarity, purpose, and soul.</p>
          <p>I don't just build digital spaces — I build connection.</p>
          <p>Through visuals, words, and strategy that feel. Because even the smallest detail can hold meaning — and I care enough to get it right.</p>
          <p>This isn't loud marketing. It's thoughtful storytelling. Not rushed content — but crafted presence.</p>
          <p>Let's build something true.</p>
          <RouterLink to="/skills" class="cta-link cta-link--light">My Skills &gt;&gt;&gt;</RouterLink>
        </div>

        <div class="photo-col">
          <div class="photo-frame">
            <div class="photo-placeholder" aria-label="Alex's headshot">📷</div>
          </div>
          <span class="deco-flower" aria-hidden="true">✿</span>
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

.photo-col {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  padding-top: 1rem;
  gap: 1.5rem;
}

.photo-frame {
  width: 260px;
  height: 280px;
  border-radius: 16px;
  overflow: hidden;
  background: #c0a898;
  box-shadow: 0 4px 24px rgba(92, 42, 20, 0.18);
  display: flex;
  align-items: center;
  justify-content: center;
}

.photo-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.photo-placeholder {
  font-size: 4rem;
  opacity: 0.4;
}

.deco-flower {
  font-size: 2.5rem;
  color: #c07a6a;
  opacity: 0.7;
}
</style>
