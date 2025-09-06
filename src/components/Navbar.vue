<template>
  <div class="navbar-container">
    <div class="logo-section">
      <img src="..\assets\summer24.JPG" alt="Stephen Kern" class="portrait">
      <h2><a href="/">Stephen Kern</a></h2>
    </div>
    <nav class="navbar">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/contact">Contact</router-link>
    </nav>
  </div>
</template>

<style scoped>
.navbar-container {
  max-width: 1600px;
  padding: 1rem;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-section{
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.portrait{
  width: 42px;
  height: 42px;
  border-radius: 50%;
  object-fit: cover;
  image-rendering: auto;
}

h2 a {
  color: floralwhite;
  font-size: 1.3rem;
}

.logo-section h2 a:hover{
  color: steelblue;
}

.navbar {
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 3em;
}

.navbar a {
  font-size: 1.2rem;
  cursor: pointer;
  color: floralwhite;
  position: relative;
}

.navbar a:hover::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  height: 5px;
  width: 100%;
  bottom: -7px;
  transition: width 0.3s ease;
  background-color: cornflowerblue;
}

.navbar .router-link-exact-active::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  height: 5px;
  width: 100%;
  bottom: -7px;
  transition: width 0.3s ease;
  background-color: steelblue;
}
</style>
