<script setup lang="ts">
interface Project {
  id: number;
  title: string;
  description: string;
}

const projects: Project[] = [
  {
    id: 1,
    title: "Portfolio Website",
    description: "A personal portfolio built with Vue + TS.",
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
