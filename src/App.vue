<script setup lang="ts">
import Navbar from "./components/Navbar.vue";
</script>

<template>
  <header>
    <Navbar />
  </header>

  <main>
    <router-view />
  </main>

  <footer>
    <p>© 2025 Stephen Kern</p>
  </footer>
</template>

<style scoped></style>
