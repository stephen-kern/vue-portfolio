<script setup lang="ts">
const email: string = "stephenkern96@gmail.com"
const linkedin: string = "https://linkedin.com/in/stephenkern96"
</script>

<template>
  <section>
    <h1>Contact</h1>
    <p>Email: <a :href="`mailto:${email}`">{{ email }}</a></p>
    <p>
      LinkedIn:
      <a :href="linkedin" target="_blank" rel="noopener noreferrer">My Profile</a>
    </p>
  </section>
</template>
