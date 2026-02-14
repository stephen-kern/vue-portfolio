<script setup lang="ts">
import resumepdf from "../assets/SK26.pdf";
import {
  Github,
  Linkedin,
  Mail,
  FileUser
} from "lucide-vue-next";
const linkedin: string = "https://linkedin.com/in/stephenkern96";
const github: string = "https://github.com/stephen-kern";
const email: string = "stephenkern96@gmail.com";

</script>

<template>
  <section class="contact-section">
    <h1>Let's Connect</h1>
    <p class="contact-intro">
      Thanks for stopping by! I enjoy meeting other developers and anyone
      interested in the web. If you want to reach out about opportunities or
      collaborations, you can find my links below.
      <br /><br />
      <span class="cta-text"
        >I usually reply within a day or two.. feel free to say hello!</span
      >
    </p>
  </section>

  <section class="contact-section">
    <h2>Find Me Online</h2>
    <div class="contact-links">
      <a class="contact-card" :href="github" target="_blank">
        <Github class="icon" />
        <span>GitHub</span>
      </a>
      <a class="contact-card" :href="linkedin" target="_blank">
        <Linkedin class="icon" />
        <span>LinkedIn</span>
      </a>
      <a class="contact-card" :href="`mailto:${email}`">
        <Mail class="icon" />
        <span>Email</span>
      </a>
      <a :href="resumepdf" class="contact-card" target="_blank">
        <FileUser class="icon"/>
        <span>Resume</span>
      </a>
    </div>
  </section>
</template>
<style scoped>

.contact-section{
  padding: 3rem 1rem;
  text-align: center;
}

.contact-intro{
  font-size: 1.35rem;
  line-height: 1.7;
  max-width: 60ch;
  margin: 0 auto 2rem;
  text-align: center;
}
p {
  max-width: 600px;
  text-align: center;
  line-height: 1.6;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
  margin-bottom: 2rem;
}

.contact-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.55rem;
  background: #FFF5E3;
  padding: 1.3rem;
  border-radius: 16px;
  width: 140px;
  text-decoration: none;
  color: var(--primary);
  transition: transform 0.2s ease, background 0.2s ease;
}

.contact-card:hover {
  transform: translateY(-4px);
  background: #f0f0f0;
}

.contact-card:active{
  border: 2px solid var(--primary);
}

.contact-card .icon {
  width: 32px;
  height: 32px;
}

.cta-text {
  text-align: left;
  margin-top: 2.5rem;
  font-style: italic;
  color: #555;
}

</style>
