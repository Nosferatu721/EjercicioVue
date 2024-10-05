<template>
  <h1>Listado de Post</h1>
  <div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4">
    <div class="flex-shrink-0">
      <img class="h-12 w-12" src="/assets/logo.png" alt="ChitChat Logo" />
    </div>
    <div>
      <div class="text-xl font-medium text-black">ChitChat</div>
      <p class="text-gray-500">You have a new message!</p>
    </div>
  </div>
  <ul class="post-list">
    <li v-for="post in posts" :key="post.id">
      <router-link :to="{ name: 'PostDetail', params: { id: post.id } }">
        {{ post.title }}
      </router-link>
    </li>
  </ul>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue';
import PostService from '@/services/PostService';

const service = new PostService();
const posts = service.getPosts();
onMounted(async () => {
  await service.fetchAll();
});
</script>

<style scoped></style>
