<template>
  <header>
    <div class="navbar-container">
      <nav class="navbar">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/projects">Projects</router-link>
        <router-link to="/contact">Contact</router-link>
      </nav>
    </div>
  </header>
</template>

<style scoped>
header {
  width: 100%;
}

.navbar-container {
  max-width: 1200px;
  padding: 1rem;
  margin: 0 auto;
}

.navbar{
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3em;
}

.navbar a{
  font-size: 1.2rem;
  cursor: pointer;
  color: floralwhite;
  position: relative;
}

.navbar a:hover {
  
}

.navbar a:hover::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  height: 3px;
  width: 100%;
  bottom: -3px;  
  transition: width 0.3s ease;
  background-color: cornflowerblue;
}
</style>
