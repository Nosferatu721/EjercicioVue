<template>
  <div class="post-container">
    <PostCard v-for="(info, i) in infos" :key="i" :title="info.title" :content="info.content" :size="info.size" @sayHi="showAlert" />
  </div>
</template>

<script lang="ts" setup>
import PostCard from './PostCard.vue';

interface IInfo {
  title: string;
  content: string;
  size: number;
}

let infos: Array<IInfo> = [
  {
    title: 'Papitas',
    content: 'Hola como tas',
    size: 415,
  },
  {
    title: 'Yucas',
    content: 'como tas',
    size: 786,
  },
  {
    title: 'Pailas',
    content: 'Hola como tas',
    size: 584,
  },
  {
    title: 'Papitas',
    content: 'Hola como tas',
    size: 415,
  },
];

function showAlert(msg: string) {
  alert(msg);
}
</script>

<style scoped>
.post-container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}
</style>
