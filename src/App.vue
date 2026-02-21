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
  max-width: 1400px;
  margin: 0 auto;
}
</style>
