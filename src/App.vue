<script setup lang="ts">
</script>

<template>
  <div>
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/contact">Contact</router-link>
    </nav>
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
