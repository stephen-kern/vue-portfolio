<script setup lang="ts">
const name: string = "Stephen";
import SkillsBar from "../components/SkillsBar.vue";
import { ChevronsDown } from "lucide-vue-next";
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
        <h1>
          <span style="font-size: 15px">Hello, I'm </span> <br />{{ name }}
        </h1>

        <h2>Detail-driven development with real-world impact</h2>

        <p>
          I'm a Front-End Developer who builds clean, user-friendly websites
          that support business goals. At Enertech Global, I develop custom
          WordPress and PHP soluutions to create smooth, responsive user
          experiences.
        </p>

        <div>
          <router-link to="/projects" class="primary-button"
            >View Projects</router-link
          >
          <router-link to="/about" class="primary-button">About Me</router-link>
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
  <section class="cta">
    <h1><span style="font-size: 15px">Hello, I'm </span> <br />{{ name }}</h1>

    <h2>Detail-driven development with real-world impact</h2>

    <div
      class="cta-space"
      :style="{
        opacity: Math.max(1 - scrollY / 550, 0), // Fade out as you scroll down
        transition: 'opacity 0.3s ease',
      }"
    >
      <h4>Check out what's down here!</h4>
      <ChevronsDown class="chevrons" :size="72" />
    </div>
  </section>
  <section class="story-section">
    <div class="story-grid">
      <img
        class="pfp"
        src="../assets/summer24square.JPG"
        alt="stephen kern in the wild"
      />

      <div>
        <p>
          I’m a Front-End Developer who builds clean, user-friendly websites
          that support business goals, and I love getting outside to recharge.
          <br /><br />
          At Enertech Global, I maintain and enhance WordPress and Joomla!
          sites, develop custom PHP features, and create AJAX-powered solutions
          for smooth user experiences.
          <br /><br />
          I’ve always been strongest on the front end, where I can bring designs
          to life with clean and functional interfaces. I’ve also explored
          backend technologies through a full-stack bootcamp, and I’m continuing
          to learn in that area so I can grow into a more versatile and
          well-rounded developer.
        </p>
        <br /><br />
        <router-link to="/about" class="primary-button">Learn More</router-link>
      </div>
    </div>
    <SkillsBar />
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

.cta {
  display: flex;
  flex-direction: column;
  text-align: center;
  height: 80vh;
  padding: 2em;
}

.cta-space {
  text-align: center;
  margin-top: auto;
}
.cta h2 {
  font-size: 4rem;
}

.story-grid {
  height: 85vh;
  padding: 2em 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

@keyframes pulse {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(6px);
  }
}

.chevrons {
  animation: pulse 2s infinite;
}

.story-grid {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 5em;
}

p {
  font-size: 1.3rem;
  line-height: 1.5;
}

.pfp {
  max-width: 500px;
  height: auto;
}

@media (max-width: 768px) {
  .hero__inner {
    flex-direction: column;
    text-align: center;
  }
}
</style>
