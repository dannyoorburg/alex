<template>
  <div class="skills">
    <section class="pg-section">

      <p class="pg-subtitle">Built on rhythm. Guided by instinct.</p>

      <div class="two-col">
        <div class="card card--salmon">
          <h2 class="card-title">🎨 Visual Design &amp; Storytelling</h2>
          <ul class="card-list">
            <li>Clean, compelling designs that guide the eye</li>
            <li>Short-form video editing with mood and flow</li>
            <li>Strong eye for aesthetic rhythm and layout</li>
            <li>Visuals that match brand tone and audience feel</li>
          </ul>
        </div>

        <div class="card card--rust">
          <h2 class="card-title">✨ Content Strategy &amp; Voice</h2>
          <ul class="card-list">
            <li>Platform-aware, audience-first planning</li>
            <li>Series-driven content with emotional impact</li>
            <li>Content that engages, nurtures, and converts</li>
            <li>Strong editorial judgment with creative flair</li>
          </ul>
          <RouterLink to="/experience" class="cta-link cta-link--dark">My Experiences &gt;&gt;&gt;</RouterLink>
        </div>
      </div>

      <p class="pg-footer">❧ Crafted with care. Delivered with clarity. ❧</p>
    </section>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<style scoped>
@import '@/assets/page.css';
</style>
