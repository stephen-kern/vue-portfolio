<script setup lang="ts">
import { onMounted } from "vue";

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

onMounted(() => {
  // Respect user's reduced motion preference
  if (window.matchMedia("(prefers-reduced-motion: reduce)").matches) return;

  const scroller = document.querySelector<HTMLElement>(".scroller");
  const inner = scroller?.querySelector<HTMLElement>(".scroller_inner");
  if (!scroller || !inner) return;

  // Mark as animated for CSS
  scroller.setAttribute("data-animated", "true");

  // Clone each icon for seamless scrolling
  const items = Array.from(inner.children);
  items.forEach((item) => {
    const clone = item.cloneNode(true) as HTMLElement;
    clone.setAttribute("aria-hidden", "true");
    inner.appendChild(clone);
  });
});
</script>

<template>
  <div class="scroller" aria-label="Technologies I've worked with">
    <div class="scroller_inner">
      <img
        v-for="(icon, i) in icons"
        :key="i"
        :src="icon.src"
        :alt="icon.alt"
        loading="lazy"
      />
    </div>
  </div>
</template>

<style>
.scroller {
  max-width: 1200px;
  margin: 0 auto 1rem;
}

.scroller_inner {
  padding-block: 1rem;
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
}

.scroller[data-animated="true"] {
  overflow: hidden;
  -webkit-mask: lineear-gradient(
    to right,
    transparent,
    white 10%,
    white 90%,
    transparent
  );
  mask: linear-gradient(
    to right,
    transparent,
    white 10%,
    white 90%,
    transparent
  );
}

.scroller[data-animated="true"] .scroller_inner {
  width: max-content;
  flex-wrap: nowrap;
  animation: scroll 30s linear infinite;
}

.scroller_inner:hover {
  animation-play-state: paused;
}

.scroller_inner img {
  height: 70px;
  width: 70px;
  flex-shrink: 0;
  user-select: none;
  transition: transform 0.2s ease;
}

.scroller_inner img:hover {
  animation-play-state: paused;
}

@keyframes scroll {
  to {
    transform: translate(calc(-50% - 1rem));
  }
}
</style>
