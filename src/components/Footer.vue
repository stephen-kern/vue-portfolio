<script setup lang="ts">
import { Github, Linkedin, Mail } from "lucide-vue-next";
const year = new Date().getFullYear();
</script>
<template>
  <footer>
    <div class="footer-social-container">
      <a
        href="https://github.com/stephen-kern"
        target="_blank"
        rel="noopener noreferrer"
        ><Github
      /></a>
      <a
        href="https://www.linkedin.com/in/stephenkern96/"
        target="_blank"
        rel="noopener noreferrer"
        ><Linkedin
      /></a>
      <a href="mailto:stephenkern96@gmail.com"><Mail /></a>
    </div>
    <p>© Stephen Kern {{ year }}</p>
  </footer>
</template>
<style scoped>
footer {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem 0;
  min-height: 3rem;
  color: white;
}

.footer-social-container {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-right: 2rem;
}

.footer-social-container a {
  color: white;
}

.footer-social-container a:hover {
  color: var(--primary-hover);
}
</style>
