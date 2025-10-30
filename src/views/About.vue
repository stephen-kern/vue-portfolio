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
    text: "I love building websites that look great and feel easy to use. Clean design and attention to detail are what keep me excited about the web! I’m always trying to write code that’s clearer and more thoughtful. At Enertech Global, I maintain and enhance our WordPress and Joomla! sites, develop custom PHP features, and keep things running fast and secure.",
    imageUrl: memoji,
    imageAlt: "Emoji of Stephen waving.",
  },
  {
    id: 2,
    text: "I’ve worked with React, Node.js, SQL, and other full-stack technologies. I enjoy projects where I can see my impact right away, but I'm also intrigued by the logic that the backend offers. I’m looking forward to expanding my skills in backend development so I can contribute to more of the process from start to finish.",
    imageUrl: fsme,
    imageAlt: "An illustration of Stephen working on a laptop.",
  },
  {
    id: 3,
    text: "Outside of coding, I spend my time with friends and family, exploring new music and art, biking, skateboarding, gaming, and planning my next travel adventure.",
    imageUrl: bike,
    imageAlt: "An illustration of Stephen on a bicycle.",
  },
];
</script>

<template>
  <section class="about-container">
    <div
      v-for="(section, index) in sections"
      :key="section.id"
      class="about"
      :class="{ reverse: index % 2 !== 0 }"
    >
      <div class="about-text">
        <p>{{ section.text }}</p>
      </div>
      <div class="about-image">
        <img :src="section.imageUrl" :alt="section.imageAlt" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-container {
  display: flex;
  flex-direction: column;
  gap: 4rem;
  padding: 2rem;
}

.about {
  display: flex;
  align-items: center;
  gap: 2rem;
}
.about.reverse {
  flex-direction: row-reverse;
}
.about-text {
  flex: 1;
  font-size: 1.1rem;
  line-height: 1.6;
}
.about-image {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.about-image img {
  width: 100%;
  max-width: 380px;
  height: auto;
  border-radius: 12px;
  object-fit: contain;
  display: block;
}
</style>
