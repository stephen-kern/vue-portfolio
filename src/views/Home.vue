<script setup lang="ts">
const name: string = "Stephen Kern";
import { ArrowBigDown } from "lucide-vue-next";
</script>

<template>
  <section class="cta">
    <h1>
      <span style="font-size: 14px">Hello, I'm </span> <br />{{ name }} 👋
    </h1>
    <h2>Detail-driven development with real-world impact</h2>

    <div class="cta-space">
      <ArrowBigDown />
    </div>
  </section>
  <section>
    <div class="story-section">
      <img
        class="pfp"
        src="../assets/summer24square.JPG"
        alt="stephen kern in the wild"
      />
      <div class="story">
        <p>
          I am a Front-End Developer passionate about building websites that are
          clean, user-friendly, and engaging.
          <br /><br />
          At Enertech Global, I maintain and improve WordPress and Joomla!
          sites, create custom PHP features, and implement AJAX-powered
          filtering to give users smooth, intuitive experiences. I enjoy solving
          problems, collaborating with teams, and writing code that’s organized
          and functional.
          <br /><br />
          My background includes earning a Full-Stack Development Certificate
          from Washington University in St. Louis, where I gained hands-on
          experience with React, Node, and SQL.
          <br /><br />
          My design approach leans toward clean and organic solutions, creating
          websites that feel natural, intuitive, and visually appealing while
          keeping functionality at the forefront.
          <br /><br />
          Outside of coding, you’ll find me exploring new music and art,
          cooking, staying active on my bike or skateboard, gaming, or planning
          my next travel adventure.
          <br /><br />
          Looking ahead, I’m excited to expand my skills into full-stack and
          backend development. I enjoy the structure, logic, and problem-solving
          these areas offer, and I’m eager to take on projects that challenge me
          to grow as a developer.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  text-align: center;
  min-height: 90vh;
}

.cta-space {
  text-align: center;
}
.cta h2 {
  font-size: 4rem;
}
.story-section {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 5em;
  flex-wrap: wrap;
}
.story {
  float: right;
  max-width: 600px;
  text-align: left;
}
.pfp {
  border-radius: 50%;
  max-width: 500px;
  height: auto;
}
</style>
