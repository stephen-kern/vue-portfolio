<script setup lang="ts">
interface Project {
  id: number;
  title: string;
  description: string;
}

const projects: Project[] = [
  {
    id: 1,
    img: "@/assets/programming.jpg",
    title: "Professional Projects",
    description:
      "Professional WordPress & web development projects available upon request",
  },
  {
    id: 2,
    img: "@/assets/Jake-Wilson-Art.png",
    title: "Fine Arts Portfolio",
    description:
      "A React-based fine arts portfolio created for a friend, with libraries from Material-UI (MUI) and EmailJS. The portfolio showcases different art forms from the artist and allows for easy communication from the viewer through a cloud-based email service.",
    ghLink: "https://github.com/stephen-kern/Jake-Wilson-Portfolio",
    liveLink: "https://jake-wilson-portfolio.vercel.app/",
  },
  {
    id: 3,
    img: "@/assets/advice-genie.png",
    title: "Advice Genie",
    description:
      "This is a simple React web app that generates a random piece of advice from the AdviceSlipAPI. Made for fun to practice API consumption.",
    ghLink: "https://github.com/stephen-kern/advicegenie",
    liveLink: "https://advicegenie.vercel.app/",
  },
  { id: 2, title: "Cool App", description: "An app that does something cool." },
];
</script>

<template>
  <section>
    <h1>Projects</h1>
    <ul>
      <li v-for="project in projects" :key="project.id">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </li>
    </ul>
  </section>
</template>

<style scoped>
.grid-container {
  display: grid;
  margin: 3rem auto;
  max-width: 70%;
}

.columns {
  display: flex;
  gap: 1rem;
}
</style>
