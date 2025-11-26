<script setup lang="ts">
const name: string = "Stephen";
// import SkillsBar from "../components/SkillsBar.vue";
// import { ChevronsDown } from "lucide-vue-next";
import { ref, onMounted, onUnmounted } from "vue";

const scrollY = ref(0);

const handleScroll = () => {
  scrollY.value = window.scrollY;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <section class="hero">
    <div class="hero__inner">
      <div class="hero__content">
        <p class="intro-label">Hello, I'm</p>
        <h1>
          {{ name }}
        </h1>

        <h2>Detail-driven development with real-world impact</h2>

        <p class="cta">
          I'm a Front-End Developer who builds clean, user-friendly websites
          that support business goals. At Enertech Global, I develop custom
          WordPress and PHP solutions to create smooth, responsive user
          experiences.
        </p>

        <div class="hero-buttons">
          <router-link to="/projects" class="primary-button"
            >View Projects</router-link
          >
          <router-link to="/about" class="secondary-button">About Me</router-link>
        </div>
      </div>
      <div class="hero__image">
        <img
          class="pfp"
          src="../assets/blob-pic.png"
          alt="stephen kern in the wild"
        />
      </div>
    </div>
  </section>
  
</template>

<style scoped>
.hero__inner {
  margin: 0 auto;
  padding: 6rem 2rem;
  max-width: 1200px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 4rem;
}

.hero__content{
  flex: 1 1 60%;
}

.intro-label{
  font-size: clamp(0.8rem, 1vw, 1rem);
  opacity: 0.9;
  line-height: 1;
  font-family: var(--font-body);
}

.hero-buttons {
  display: flex;
  gap: 2.5rem;
  margin-top: 2rem;
}

.cta{
  font-size: clamp(0.9rem, 5vw, 1.3rem);
  line-height: 1.5;
  font-family: var(--font-body);
}

.hero__image{
  flex: 1 1 40%;
  display: flex;
  justify-content: center;
}

.pfp {
  max-width: clamp(300px, 40vw, 100%);
  height: auto;
}

@media (max-width: 968px) {
  .hero__inner {
    flex-direction: column;
    text-align: center;
    gap: 2rem;
    padding: 2rem 0.5rem;
  }

  .hero__content{
    flex: none;
  }

  .hero-buttons{
    justify-content: center;
  }
}
</style>
