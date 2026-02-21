<template>
  <div class="experience">
    <section class="pg-section">
      <div class="stamp stamp--top-left">Mood. Motion. Meaning...<br>This is your moment.</div>
      <div class="stamp stamp--top-right">Reels with Rhythm.<br>Content with Heart.</div>

      <div class="pg-header">
        <h1 class="pg-title">Built on story</h1>
        <div class="pg-divider"><span class="div-line"/><span class="div-heart">♡</span><span class="div-line"/></div>
      </div>

      <p class="pg-subtitle">Shaped by experience. Led with heart. <span class="deco-quill">🪶</span></p>

      <div class="two-col">
        <div class="card card--salmon">
          <h2 class="card-title">🎙 Storytelling Roots</h2>
          <ul class="card-list">
            <li>20 years in journalism, research &amp; TV production</li>
            <li>Researcher — digging deep for the truth behind the story</li>
            <li>Producer — bringing vision to life, frame by frame</li>
            <li>Journalist — giving voice to the stories that matter</li>
            <li>Now: Content Strategist &amp; Visual Storyteller</li>
          </ul>
        </div>

        <div class="card card--rust">
          <h2 class="card-title">💡 A Personal Approach</h2>
          <ul class="card-list">
            <li>Not a full-stack agency — a single, dedicated creative</li>
            <li>Human-first, heart-led content strategy</li>
            <li>Your story told with care, craft, and clarity</li>
            <li>Every project handled with personal attention</li>
          </ul>
          <RouterLink to="/services" class="cta-link cta-link--dark">My Services &gt;&gt;&gt;</RouterLink>
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
</style>
