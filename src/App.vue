<script setup lang="ts">
import Footer from "./components/Footer.vue";
import Navbar from "./components/Navbar.vue";
</script>

<template>
  <header>
    <Navbar />
  </header>

  <main>
    <router-view />
  </main>

  <Footer />
</template>

<style scoped>

</style>
