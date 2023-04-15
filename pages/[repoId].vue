<script setup lang="ts">
import Repo from '~/types/data';

const route = useRoute()
//TODO Show Topics
//const topics = route.query["topics[]"]

const repo: Repo = {
  name: String(route.query.name),
  description: String(route.query.description),
  id: Number(route.params.id),
  language: String(route.query.language),
  topics: [],
}

</script>

<template>
  <RepoDetail :repo="repo" />
</template>
