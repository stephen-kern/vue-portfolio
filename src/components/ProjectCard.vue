<script setup lang="ts">

interface ProjectCardProps {
  title: string;
  description: string;
  img?: string;
  ghLink?: string;
  liveLink?: string;
}

const props = defineProps<ProjectCardProps>();
</script>

<template>
  <div class="card">
    <div class="img-container">
      <img
        v-if="props.img"
        :src="props.img"
        :alt="props.title + ' project screenshot'"
        class="card__img"
      />
    </div>
    <div class="card-info">
      <h3 class="card-title">{{ props.title }}</h3>
      <p class="card-description">{{ props.description }}</p>
      <div class="card-buttons">
        <button v-if="props.ghLink" class="primary-button">
          <a :href="props.ghLink" target="_blank" rel="noopener noreferer"
            >GitHub Link</a
          >
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  border-radius: 0.2rem;
  background: white;
  padding: 0;
  min-width: 400px;
}
.img-container {

  border-radius: 0.2rem 0.2rem 0 0;
}

.card__img {
  max-width: 100%;
  height: 300px;
  object-fit: cover;
}

.card-info {
  padding: 1rem;
  text-align: center;
}

.card-title {
  margin: 0.5rem 0;
  font-size: 1.25rem;
  color:#555
}
.card-description {
  font-size: 1rem;
  color: #555;
}
.card-buttons {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  margin-top: 1rem;
}
button {
  border: none;
}
button a {
  color: white;
  text-decoration: none;
}
</style>
