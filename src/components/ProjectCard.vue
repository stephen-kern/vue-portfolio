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
      class="Card__img"
    />
    <h3 class="card__title">{{ props.title }}</h3>
    <p class="card__info">{{ props.description }}</p>

    <div class="card__links">
      <button v-if="props.ghLink">
        <a :href="props.ghLink" target="_blank" rel="noopener noreferer"
          >GitHub Link</a
        >
      </button>
    </div>
  </div>
</template>

<style scoped>
.card {
  border-radius: 8px;
  padding: 1.5rem;
  text-align: center;
  background: white;
}
.card__img {
  max-width: 100%;
  border-radius: 4px;
}
.card__title {
  margin: 0.5rem 0;
  font-size: 1.25rem;
}
.card__info {
  font-size: 1rem;
  color: #555;
}
.card__links {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  margin-top: 1rem;
}
button {
  border: none;
  background: #222;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 4px;
}
button a {
  color: white;
  text-decoration: none;
}
</style>
