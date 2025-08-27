<template>
  <header>
    <div class="navbar-container">
      <nav class="navbar">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/projects">Projects</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.navbar {
  background-color: aliceblue;
}

.navbar ul {
  list-style: none;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.3rem;
  padding: 0;
}

.navbar ul li {
  font-size: 1.2rem;
  cursor: pointer;
}

li a {
  color: black;
}

header nav ul li a:hover {
  color: green;
}
</style>
