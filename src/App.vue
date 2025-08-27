<script setup lang="ts">
import Navbar from './components/Navbar.vue';
</script>

<template>
  <div>
    <Navbar />
    <main>
      <router-view />
    </main>
    <footer>
      <p>© 2025 Stephen Kern</p>
    </footer>
  </div>
</template>

<style scoped>

</style>
