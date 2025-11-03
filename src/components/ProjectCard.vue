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
    <img
      v-if="props.img"
      :src="props.img"
      :alt="props.title + ' project screenshot'"
      class="card-image"
    />

    <div class="card-info">
      <h3 class="card-title">{{ props.title }}</h3>
      <p class="card-description">{{ props.description }}</p>
      <div class="card-buttons">
        <button v-if="props.liveLink" class="primary-button">
          <a :href="props.liveLink" target="_blank" rel="noopener noreferer"
            >Learn More</a
          >
        </button>

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
  border-radius: 2rem 2rem 1rem 1rem;
  background: white;
  padding: 0;
  min-width: 400px;
  width: 100%;
}

.card-image {
  max-width: 100%;
  object-fit: cover;
  border-radius: 1rem 1rem 0 0
}

.card-info {
  padding: 1rem 2rem 1.5rem;
  text-align: center;
}

.card-title {
  margin: 0.5rem 0;
  font-size: 1.25rem;
  color: #555;
}
.card-description {
  font-size: 1rem;
  color: #555;
}
.card-buttons {
  display: flex;
  justify-content: center;
  gap: 2.5rem;
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
