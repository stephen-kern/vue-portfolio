<script setup lang="ts">
import Card from "../components/ProjectCard.vue";
import jwp from "../assets/Jake-Wilson-Art.webp";
import workcard from "../assets/programming.webp";
import advgen from "../assets/advice-genie.webp";

interface Project {
  id: number;
  title: string;
  description: string;
  img?: string;
  ghLink?: string;
  liveLink?: string;
}

const projectsData: Project[] = [
  {
    id: 1,
    title: "Professional Projects",
    description:
      "Professional WordPress & web development projects available upon request. For more information, please checkout my resume found on my contact page.",
    liveLink: "/contact",
    img: workcard,
  },
  {
    id: 2,
    title: "Fine Arts Portfolio",
    description:
      "A React-based fine arts portfolio created for a friend. It uses MUI for structure and styling, React-Modal-Image for interactive galleries, and EmailJS for simple, secure form submissions.",
    ghLink: "https://github.com/stephen-kern/Jake-Wilson-Portfolio",
    liveLink: "https://jake-wilson-portfolio.vercel.app/",
    img: jwp,
  },
  {
    id: 3,
    title: "Advice Genie",
    description:
      "This is a straighforward React web app that generates a random piece of advice from the AdviceSlipAPI. Made for fun to practice API consumption.",
    ghLink: "https://github.com/stephen-kern/advicegenie",
    liveLink: "https://advicegenie.vercel.app/",
    img: advgen,
  },
];

const tba = "More projects and case studies coming soon.";
</script>

<template>
  <section class="grid-section">
    <h2>Projects</h2>
    <div class="card-grid">
      <Card
        v-for="project in projectsData"
        :key="project.id"
        :img="project.img"
        :title="project.title"
        :description="project.description"
        :gh-link="project.ghLink"
        :live-link="project.liveLink"
      />
    </div>
  </section>
  <section class="tba-section">
    <div>
      <p class="tba-text">{{ tba }}</p>
    </div>
  </section>
</template>

<style scoped>
section {
  padding: 1rem 0;
  margin: 1rem 0;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));

  gap: 1.5rem;
  padding: 1.5rem;
}

.tba-text {
  color: var(--secondary);
  font-size: 18px;
  text-align: center;
}

@media screen and (max-width: 768px) {
  h2 {
    text-align: center;
  }

  .card-grid {
    gap: 2rem;
    place-items: center;
  }
}
</style>
