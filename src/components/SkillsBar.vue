<script setup lang="ts">
const icons = [
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/wordpress/wordpress-plain.svg",
    alt: "WordPress",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
    alt: "HTML5",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg",
    alt: "CSS3",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
    alt: "JavaScript",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg",
    alt: "TypeScript",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg",
    alt: "React",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg",
    alt: "Vue.js",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg",
    alt: "Node.js",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg",
    alt: "PHP",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg",
    alt: "Git",
  },
  {
    src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg",
    alt: "GitHub",
  },
];
</script>

<template>
  <div class="skills-carousel">
    <div class="carousel-track">
      <img
        v-for="(icon, i) in icons"
        :key="i"
        :src="icon.src"
        :alt="icon.alt"
      />
      <!-- Duplicate the icons for seamless scrolling -->
      <img
        v-for="(icon, i) in icons"
        :key="'dup-' + i"
        :src="icon.src"
        :alt="icon.alt"
      />
    </div>
  </div>
</template>

<style scoped>
.skills-carousel {
  overflow: hidden;
  width: 100%;
  padding: 1rem 0;
}

.carousel-track {
  display: flex;
  gap: 2rem;
  animation: scroll 20s linear infinite;
  width: max-content;
}

.carousel-track img {
  height: 50px;
  width: 50px;
  flex-shrink: 0;
}

@keyframes scroll {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-50%);
  }
}
</style>
