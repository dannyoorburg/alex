<template>
  <div class="landing">
    <header class="header">
      <nav class="nav">
        <span class="logo">Alex</span>
        <ul class="nav-links">
          <li><a href="#about">About</a></li>
          <li><a href="#features">Features</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title">Welcome to <span class="accent">Alex</span></h1>
        <p class="hero-subtitle">A simple, modern Vue 3 website — ready for you to build on.</p>
        <div class="hero-actions">
          <a href="#features" class="btn btn-primary">Get Started</a>
          <a href="#about" class="btn btn-secondary">Learn More</a>
        </div>
      </div>
      <div class="hero-graphic">
        <div class="circle circle-lg"></div>
        <div class="circle circle-md"></div>
        <div class="circle circle-sm"></div>
      </div>
    </section>

    <section id="about" class="section">
      <h2>About</h2>
      <p>
        This site is built with <strong>Vue 3</strong> and <strong>Vite</strong> — a lightning-fast
        development setup that makes building modern web apps a breeze.
      </p>
    </section>

    <section id="features" class="section features">
      <h2>Features</h2>
      <div class="cards">
        <div class="card" v-for="feature in features" :key="feature.title">
          <div class="card-icon">{{ feature.icon }}</div>
          <h3>{{ feature.title }}</h3>
          <p>{{ feature.description }}</p>
        </div>
      </div>
    </section>

    <section id="contact" class="section contact">
      <h2>Get in Touch</h2>
      <p>Have a question or just want to say hi? Reach out!</p>
      <a href="mailto:hello@example.com" class="btn btn-primary">Say Hello</a>
    </section>

    <footer class="footer">
      <p>&copy; {{ year }} Alex. Built with Vue 3 + Vite.</p>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface Feature {
  icon: string
  title: string
  description: string
}

const year = computed<number>(() => new Date().getFullYear())

const features: Feature[] = [
  {
    icon: '⚡',
    title: 'Fast',
    description: 'Powered by Vite for instant HMR and blazing-fast builds.',
  },
  {
    icon: '🧩',
    title: 'Component-Based',
    description: 'Build UIs with reusable, composable Vue 3 components.',
  },
  {
    icon: '🎨',
    title: 'Customisable',
    description: 'Easily tweak styles, add pages, or extend with plugins.',
  },
]
</script>
