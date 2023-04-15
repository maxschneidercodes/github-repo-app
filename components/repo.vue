<script setup lang="ts">
import Repo from '~/types/data';

defineProps<{
  repo: Repo
}>()
</script>

<template>
  <div class="card m-4" style="width: 20rem;">
    <div class="card-body">
      <h5 class="card-title">{{ repo.name }}</h5>
      <p class="card-text">{{ repo.description }}</p>
      <NuxtLink class="btn btn-primary" :to="{
        path: '/' + repo.id,
        query: {
          id: repo.id,
          name: repo.name,
          language: repo.language,
          description: repo.description,
          'topics[]': repo.topics
        }
      }">mehr</NuxtLink>
    </div>
  </div>
</template>

