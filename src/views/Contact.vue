<script setup lang="ts">
import {
  Github,
  Linkedin,
  Mail,
  Pin,
  Handshake,
  MessageCircleCode,
} from "lucide-vue-next";
const linkedin: string = "https://linkedin.com/in/stephenkern96";
const github: string = "https://github.com/stephen-kern";
const email: string = "stephenkern96@gmail.com";
</script>

<template>
  <section>
    <h1>Let's Connect</h1>
    <p>
      Thanks for stopping by! I enjoy meeting other developers and anyone
      interested in the web. If you want to reach out about opportunities or
      collaborations, you can find my links below.
      <br /><br />
      <span class="cta-text"
        >I usually reply within a day or two.. feel free to say hello!</span
      >
    </p>
    <h2>Where You Can Find Me</h2>
    <div class="contact-links">
      <a class="contact-card" :href="github" target="_blank">
        <Github class="icon" />
        <span>GitHub Profile</span>
      </a>

      <a class="contact-card" :href="linkedin" target="_blank">
        <Linkedin class="icon" />
        <span>LinkedIn</span>
      </a>

      <a class="contact-card" :href="`mailto:${email}`">
        <Mail class="icon" />
        <span>Email</span>
      </a>

      <ul class="contact-list">
        <li><Pin class="pin" />Open to web development opportunities</li>
        <li><Handshake class="handshake"/> for collaboration or side projects</li>
        <li><MessageCircleCode class="message"/> to answer questions about my work</li>
      </ul>
    </div>
  </section>
</template>
<style scoped>
h1 {
  font-size: 3rem;
  margin-bottom: 0.5em;
}

p {
  max-width: 600px;
  text-align: center;
  line-height: 1.6;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  font-size: 1.75rem;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
  margin-bottom: 2rem;
}

.contact-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
  background: #f8f8f8;
  padding: 1.5rem;
  border-radius: 16px;
  width: 140px;
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s ease, background 0.2s ease;
}

.contact-card:hover {
  transform: translateY(-4px);
  background: #f0f0f0;
}

.contact-card .icon {
  width: 36px;
  height: 36px;
}

.contact-list {
  list-style: none;
  padding: 0;
  max-width: 500px;
  margin: 0 auto;
  text-align: left;
}

.contact-list li {
  margin: 0.5rem 0;
  font-size: 1.1rem;
}

.cta-text {
  text-align: left;
  margin-top: 2.5rem;
  font-style: italic;
  color: #555;
}
</style>
