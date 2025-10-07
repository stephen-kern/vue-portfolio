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

const repeats = 2;

const repeatedIcons = Array.from({ length: repeats }, () => icons).flat();
</script>

<template>
  <div class="ticker">
    <div class="ticker-track">
      <img
        v-for="(icon, i) in repeatedIcons"
        :key="i"
        :src="icon.src"
        :alt="icon.alt"
      />
    </div>
  </div>
</template>

<style scoped>
.ticker {
  overflow: hidden;
  width: 90%;
  margin: 0 auto;
}

.ticker-track {
  display: flex;
  gap: 2rem;
  animation: scroll 10s linear infinite;
}

.ticker-track img {
  height: 80px;
  width: 80px;
  flex-shrink: 0;
  user-select: none;
}

.ticker-track img:hover {
  animation-play-state: paused;
} 

@keyframes scroll {
  from {
    transform: translateX(0%); /* scroll by 1 set's width if 3 repeats */
  } to {
    transform: translateX(-33.333%); /* scroll by 1 set's width if 3 repeats */
  }
}
</style>
