<script setup lang="ts">
import { ref } from "vue";

const isOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
  document.body.classList.toggle("no-scroll", isOpen.value);
};

const navLinks = [
  { label: "Home", to: "/" },
  { label: "Projects", to: "/projects" },
  { label: "About", to: "/about" },
  { label: "Contact", to: "/contact" },
];

const socialLinks = [
  { label: "GitHub", href: "https://github.com/stephen-kern" },
  { label: "LinkedIn", href: "https://www.linkedin.com/in/stephenkern96/" },
  { label: "Email", href: "mailto:stephenkern96@gmail.com" },
];
</script>

<template>
  <header class="navbar-container">
    <RouterLink to="/" class="logo-link" aria-label="Go to home">
      <img
        src="../assets/navbar-icon.webp"
        alt="Initials SK in favicon logo"
        class="logo"
      />
    </RouterLink>

    <!-- Hamburger Button -->
    <button
      class="hamburger"
      @click="toggleMenu"
      aria-label="Menu"
      :aria-expanded="isOpen"
      :class="{ open: isOpen }"
    >
      <span class="bar"></span>
      <span class="bar"></span>
    </button>

    <!-- Desktop Nav -->
    <nav class="desktop-nav">
      <RouterLink
        v-for="item in navLinks"
        :key="item.to"
        :to="item.to"
      >
        {{ item.label }}
      </RouterLink>
    </nav>

    <!-- Mobile Menu -->
    <transition name="slide">
      <aside v-if="isOpen" class="mobile-nav">
        <div class="mobile-nav-links">
          <RouterLink
            v-for="item in navLinks"
            :key="item.to"
            :to="item.to"
            @click="toggleMenu"
          >
            {{ item.label }}
          </RouterLink>
        </div>

        <div class="divider"></div>

        <div class="social-links">
          <a
            v-for="s in socialLinks"
            :key="s.href"
            :href="s.href"
            target="_blank"
            rel="noopener noreferrer"
          >
            {{ s.label }}
          </a>
        </div>
      </aside>
    </transition>
  </header>

  <!-- Backdrop -->
  <div
    v-if="isOpen"
    class="backdrop"
    @click="toggleMenu"
    aria-hidden="true"
  ></div>
</template>

<style scoped>
.navbar-container {
  margin: 2rem auto;
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
  color: var(--text);
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
  background: var(--text);
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
  background: rgba(0, 0, 0, 0.8);
  z-index: 900;
  overflow: hidden;
}

.mobile-nav {
  position: fixed;
  top: 0;
  right: 0;
  overflow: hidden;
  height: 100dvh;
  height: 100vh;
  width: min(70%, 300px);
  background-color: #212121;
  padding: 2rem 1.5rem;
  box-shadow: -2px 0 10px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  z-index: 1000;
  border-left: 2px solid var(--primary);
}


.mobile-nav-links {
  display: flex;
  flex-direction: column;
  margin: 2.5rem 0;
  gap: 1.5rem;
}

.mobile-nav-links a {
  color: var(--text);
  font-size: 1.5rem;
  font-weight: 500;
}

.mobile-nav .mobile-nav-links a:active,
.mobile-nav .mobile-nav-links a:focus-visible,
.social-links a:active,
.social-links a:focus-visible {
  color: var(--primary);
  transform: scale(0.98); /* subtle press effect */
}

.mobile-nav .divider {
  width: 100%;
  height: 1px;
  background-color: var(--divider);
  margin: 2rem 0;
}

/* Social links container */
.mobile-nav .social-links {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.mobile-nav .social-links a {
  font-size: 1.25rem;
  color: #ffffff;
  transition: color 0.25s ease, transform 0.2s ease;
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
