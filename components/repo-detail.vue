<script setup lang="ts">
import Repo from '~/types/data';
defineProps<{
    repo: Repo
}>()
</script>

<template>
    <h1 class="card-title">{{ repo.name }}</h1>
    <p class="card-text">{{ repo.description }}</p>
    <div v-for="item in repo.topics">
        <p class="badge text-bg-secondary">{{ item }}</p>
    </div>
</template>