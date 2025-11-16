<script setup lang="ts">
import { ref } from "vue";

const isOpen = ref(false);
const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
</script>

<template>
  <div class="navbar-container">
    <a href="/" class="logo-link">
      <img
        src="../assets/navbar-icon.webp"
        alt="Initials SK in favicon logo"
        class="logo"
      />
    </a>

    <!-- Hamburger Menu -->
    <button
      class="hamburger"
      @click="toggleMenu"
      aria-label="Toggle Menu"
      :class="{ open: isOpen }"
    >
      <span class="bar"></span>
      <span class="bar"></span>
    </button>

    <!-- Desktop Navigation -->
    <nav class="desktop-nav">
      <router-link to="/">Home</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/contact">Contact</router-link>
    </nav>

    <!-- Mobile Off-Canvas Navigation -->
    <transition name="slide">
      <aside v-if="isOpen" class="mobile-nav">
        <router-link to="/" @click="toggleMenu">Home</router-link>
        <router-link to="/projects" @click="toggleMenu">Projects</router-link>
        <router-link to="/about" @click="toggleMenu">About</router-link>
        <router-link to="/contact" @click="toggleMenu">Contact</router-link>
      </aside>
    </transition>
  </div>
  <div v-if="isOpen" class="backdrop" @click="toggleMenu"></div>
</template>

<style scoped>
.navbar-container {
  padding: 1rem 2rem;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  width: 38px;
  height: 38px;
  object-fit: cover;
  image-rendering: auto;
  align-items: center;
}

h2 a {
  color: #fff;
  font-size: 1.3rem;
}

.logo-section h2 a:hover {
  color: var(--primary-hover);
}

/* Desktop Nav styles  */
.desktop-nav {
  display: flex;
  gap: 3rem;
}

.desktop-nav a {
  font-size: 1.2rem;
  cursor: pointer;
  color: white;
  position: relative;
}

.desktop-nav a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -7px;
  height: 5px;
  width: 0%;
  transition: width 0.3s ease;
  background-color: var(--primary);
}

.desktop-nav a:hover::after {
  width: 100%;
}

.desktop-nav .router-link-exact-active::after {
  width: 100%;
  background-color: var(--primary);
}

/* Hamburger Menu styles */
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 12px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001;
}

.bar {
  display: block;
  height: 3px;
  width: 100%;
  background: #fff;
  border-radius: 3px;
  transition: all 0.4s ease;
}

.hamburger.open .bar:nth-child(1) {
  transform: rotate(45deg) translate(3px, 3px);
}

.hamburger.open .bar:nth-child(2) {
  transform: rotate(-45deg) translate(3px, -3px);
}

.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100dvh;
  background: rgba(0, 0, 0, 0.5);
  z-index: 900;
}

.mobile-nav {
  position: fixed;
  top: 0;
  right: 0;
  height: 100dvh;
  width: min(80%, 300px);
  background-color: #212121;
  padding: 2rem 1.5rem;
  box-shadow: -2px 0 5px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  gap: 2rem;
  z-index: 1000;
}

.mobile-nav a {
  color: floralwhite;
  font-size: 1.5rem;
}

/* Slide animation */
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.3s ease;
}
.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
}

/* Responsive Rules */
@media (max-width: 768px) {
  .desktop-nav {
    display: none;
  }
  .hamburger {
    display: flex;
  }
}
</style>
