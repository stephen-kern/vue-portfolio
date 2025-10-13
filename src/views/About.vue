<script setup lang="ts">
interface Section {
  id: number;
  text: string;
  imageUrl: string;
  imageAlt: string;
}

const sections: Section[] = [
  {
    id: 1,
    text: "I’m a front-end developer who enjoys building clean, easy-to-use websites. I currently work at Enertech Global, where I maintain and improve WordPress and Joomla! sites, create custom PHP features, and focus on improving site performance and security.",
    imageUrl: "../assets/summer24.JPG",
    imageAlt: "A photo of Stephen Kern",
  },
  {
    id: 2,
    text: "I’ve worked with React, Node.js, SQL, and other full-stack technologies. I enjoy projects where I can see my impact right away, but I'm also intrigued by the logic that the backend offers. I’m looking forward to expanding my skills in backend development so I can contribute to more of the process from start to finish.",
    imageUrl: "../assets/stephen-kern.jpg",
    imageAlt: "An illustration of front-end and back-end development concepts.",
  },
  {
    id: 3,
    text: "Outside of coding, I spend my time with friends and family, exploring new music and art, biking, skateboarding, gaming, and planning my next travel adventure.",
    imageUrl: "../assets/stephen-kern.jpg",
    imageAlt: "An illustration of a man on a bicycle.",
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

  .about{
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
  }
  .about-image img {
    width: 100%;
    height: auto;
    border-radius: 12px;
    object-fit: cover;
  }
</style>