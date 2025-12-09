<script setup lang="ts">
interface ProjectCardProps {
  title: string;
  description: string;
  img?: string;
  links?: Array<{ label: string; url: string; type?: "internal" | "external" }>;
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

    <div class="card-content">
      <div class="card-info">
        <h3 class="card-title">{{ props.title }}</h3>
        <p class="card-description">{{ props.description }}</p>
      </div>
      <div v-if="props.links" class="card-buttons">
        <template v-for="(link, index) in props.links" :key="index">
          <router-link
            v-if="link.type === 'internal'"
            :to="link.url"
            :class="index === 0 ? 'primary-button' : 'secondary-button'"
          >
            {{ link.label }}
          </router-link>

          <a
            v-else
            :href="link.url"
            target="_blank"
            rel="noopener noreferrer"
            :class="index === 0 ? 'primary-button' : 'secondary-button'"
          >
            {{ link.label }}
          </a>
        </template>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  border-radius: 2rem 2rem 1rem 1rem;
  background: var(--divider);
  padding: 0;
  min-width: 300px;
  max-width: 400px;
  width: 100%;
}

.card-image {
  max-width: 100%;
  object-fit: cover;
  border-radius: 1rem 1rem 0 0;
}

.card-content {
  padding: 1rem 2rem 1.5rem;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-content: space-between;
}

.card-title {
  margin: 0.5rem 0;
  font-size: 1.25rem;
  color: #555;
}
.card-description {
  font-size: 1rem;
  color: #555;
  flex: 1;
}
.card-buttons {
  display: flex;
  justify-content: center;
  gap: 2.5rem;
  margin-top: 1rem;
}

@media screen and (max-width: 678px) {
  .card-buttons {
    gap: 1.5rem;
  }
}
</style>
