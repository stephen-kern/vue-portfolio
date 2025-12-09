<script setup lang="ts">
import Card from "../components/ProjectCard.vue";
import jwp from "../assets/Jake-Wilson-Art.webp";
import workcard from "../assets/programming.webp";
import advgen from "../assets/advice-genie.webp";

interface ProjectLink {
  label: string;
  type: "internal" | "external";
  url: string;
}

interface Project {
  id: number;
  title: string;
  description: string;
  img?: string;
  ghLink?: string;
  liveLink?: string;
  links: ProjectLink[];
}

const projectsData: Project[] = [
  {
    id: 1,
    title: "Professional Projects",
    description:
      "Professional WordPress & web development projects available upon request. For more information, please checkout my resume found on my contact page.",
    img: workcard,
    links: [
      {
        label: "Contact Me",
        type: "internal",
        url: "/contact",
      },
    ],
  },
  {
    id: 2,
    title: "Fine Arts Portfolio",
    description:
      "A React-based fine arts portfolio created for a friend. It uses MUI for structure and styling, React-Modal-Image for interactive galleries, and EmailJS for simple, secure form submissions.",
    img: jwp,
    links: [
      {
        label: "View Live",
        type: "external",
        url: "https://jake-wilson-portfolio.vercel.app/",
      },
      {
        label: "View Code",
        type: "external",
        url: "https://github.com/stephen-kern/Jake-Wilson-Portfolio",
      },
    ],
  },
  {
    id: 3,
    title: "Advice Genie",
    description:
      "A simple web app that fetches a random piece of advice from the AdviceSlipAPI. It was built as a small project to practice working with APIs, managing state, and structuring components in React.",
    img: advgen,
    links: [
      {
        label: "View Live",
        type: "external",
        url: "https://advicegenie.vercel.app/",
      },
      {
        label: "View Code",
        type: "external",
        url: "https://github.com/stephen-kern/advicegenie",
      },
    ],
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
        :links="project.links"
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
