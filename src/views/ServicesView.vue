<template>
  <div class="services">
    <section class="pg-section">
      <div class="stamp stamp--top-left">Mood. Motion. Meaning...<br>This is your moment.</div>
      <div class="stamp stamp--top-right">Reels with Rhythm.<br>Content with Heart.</div>

      <p class="pg-subtitle">Strategy-led content &amp; design for digital presence</p>

      <div class="two-col">
        <div class="card card--salmon">
          <h2 class="card-title">?? Social Media Support</h2>
          <ul class="card-list">
            <li>Instagram strategy &amp; brand voice</li>
            <li>Reels series concepts + light editing</li>
            <li>Campaign ideas &amp; execution</li>
            <li>Social media visuals (Stories, Reels...)</li>
          </ul>
        </div>

        <div class="card card--rust">
          <h2 class="card-title">?? Website &amp; Brand Presence</h2>
          <ul class="card-list">
            <li>Website layout &amp; homepage design</li>
            <li>Brand kits (colours, fonts, tone, voice)</li>
            <li>Website copy (Bios, pitches, headlines)</li>
            <li>Visual storytelling for small brands</li>
          </ul>
          <RouterLink to="/portfolio" class="cta-link cta-link--dark">My Portfolio &gt;&gt;&gt;</RouterLink>
        </div>
      </div>

      <p class="pg-footer">? All services are customisable. Let's chat ?</p>
    </section>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
@import '@/assets/page.css';
</style>
