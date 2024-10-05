<template>
  <h1>Post Detail</h1>
  <div class="post-container">
    <div class="post-card">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue';
import { useRoute } from 'vue-router';
import PostService from '@/services/PostService';

const service = new PostService();
const post = service.getPost();

onMounted(async () => {
  const route = useRoute();
  let elm = route.params.id;
  await service.fetchByID(elm);
});
</script>
