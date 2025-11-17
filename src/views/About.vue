<script setup lang="ts">
import memoji from "../assets/nobg-memoji.webp";
import fsme from "../assets/fsme.webp";
import bike from "../assets/me-on-bike-nobg.webp";

interface Section {
  id: number;
  text: string;
  imageUrl: string;
  imageAlt: string;
}

const sections: Section[] = [
  {
    id: 1,
    text: "I love building websites that look great and feel easy to use. Clean design and attention to detail are what keep me excited about the web! I’m always trying to write code that’s clearer and more thoughtful than the last. Right now I work at Enertech Global and I maintain and enhance our WordPress and Joomla! sites, develop custom features, and keep things running fast and secure.",
    imageUrl: memoji,
    imageAlt: "Emoji of Stephen waving.",
  },
  {
    id: 2,
    text: "Most of my day-to-day work involves CMS theme builders, but I also create custom solutions with HTML, CSS, JS, and PHP when needed. I like keeping my code organized and efficient, and often consider ways to make it even better. While I’ve mostly worked with WordPress backend setups, I’m excited to continue growing my skills in backend development and working with data.",
    imageUrl: fsme,
    imageAlt: "An illustration of Stephen working on a laptop.",
  },
  {
    id: 3,
    text: "Outside of work, I enjoy a mix of activities that keep me energized. You might find me spending time with friends and family, planning my next adventure, exploring new music and art, skateboarding, gaming, or riding my bike!",
    imageUrl: bike,
    imageAlt: "An illustration of Stephen on a bicycle.",
  },
];
</script>

<template>
  <section class="about-container">
    <h2>More About Me</h2>
    <div
      v-for="(section, index) in sections"
      :key="section.id"
      class="about"
      :class="[{ reverse: index % 2 !== 0 }, { 'img-large': index === 1 }, { 'img-small': index === 2 }]"
    >
      <div class="about-text">
        <p>{{ section.text }}</p>
      </div>

      <img
        :src="section.imageUrl"
        :alt="section.imageAlt"
        loading="lazy"
        decoding="async"
        fetchpriority="low"
        width="350"
        height="350"
      />
    </div>
  </section>
</template>

<style scoped>
.about-container {
  display: flex;
  flex-direction: column;
  gap: 3rem;
  padding: 1rem 2rem;
}

.about-container h2 {
  margin-bottom: 1rem;
}

.about {
  display: flex;
  align-items: center;
  gap: 4rem;
}
.about.reverse {
  flex-direction: row-reverse;
}
.about-text {
  flex: 1;
  text-align: left;
  font-size: 1.3rem;
  line-height: 1.6;
}

img {
  width: 100%;
  max-width: 350px;
  height: auto;
  border-radius: 12px;
  object-fit: contain;
  display: block;
}


.img-large img {
  max-width: 450px;
}

@media (max-width: 768px) {
  .about-container h2 {
    text-align: center;
  }
  .about {
    flex-direction: column-reverse;
    gap: 2rem;
  }
  .about.reverse {
    flex-direction: column-reverse;
  }
  .about-text {
    font-size: 1.1rem;
    text-align: center;
  }
  img {
    max-width: 280px;
  }
  .img-large img {
    max-width: 350px;
  }
  .img-small img {
    max-width: 250px;
  }
}
</style>
