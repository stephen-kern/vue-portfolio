<script setup lang="ts">
import Card from "../components/ProjectCard.vue";
import jwp from '../assets/Jake-Wilson-Art.png';
import workcard from "../assets/programming.jpg";
import advgen from "../assets/advice-genie.png";

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
      "Professional WordPress & web development projects available upon request. Check out my resume for more information.",
    img: workcard
  },
  {
    id: 2,
    title: "Fine Arts Portfolio",
    description:
      "A React-based fine arts portfolio created for a friend, with libraries from Material-UI (MUI) and EmailJS. The portfolio showcases different art forms from the artist and allows for easy communication from the viewer through a cloud-based email service.",
    ghLink: "https://github.com/stephen-kern/Jake-Wilson-Portfolio",
    liveLink: "https://jake-wilson-portfolio.vercel.app/",
    img: jwp
  },
  {
    id: 3,
    title: "Advice Genie",
    description:
      "This is a simple React web app that generates a random piece of advice from the AdviceSlipAPI. Made for fun to practice API consumption.",
    ghLink: "https://github.com/stephen-kern/advicegenie",
    liveLink: "https://advicegenie.vercel.app/",
    img: advgen
  },
];
</script>

<template>
  <section id="projects-section" class="grid-container">
    <h2 class="section-title">Projects</h2>
    <div class="columns">
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
</template>

<style scoped>


.columns {
  display: flex;
  gap: 2rem;
  justify-content: center;
}
</style>
