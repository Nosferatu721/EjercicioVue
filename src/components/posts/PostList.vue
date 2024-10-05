<template>
  <h1>Listado de Post</h1>
  <ul class="post-list">
    <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
  </ul>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue';
import PostService from '@/services/PostService';

const service = new PostService();
const posts = service.getPost();
onMounted(async () => {
  await service.fetchAll();
});
</script>

<style scoped></style>
