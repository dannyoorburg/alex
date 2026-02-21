<template>
  <div class="app-wrapper">
    <NavBar />
    <main>
      <RouterView />
    </main>
  </div>
</template>

<script setup lang="ts">
import NavBar from '@/components/NavBar.vue'
</script>

<style scoped>
.app-wrapper {
  max-width: 1200px;
  margin: 0 auto;
  /* brick bg shows on body; shadow frames the content column */
  box-shadow: 0 0 60px rgba(92, 42, 20, 0.08);
}
</style>
