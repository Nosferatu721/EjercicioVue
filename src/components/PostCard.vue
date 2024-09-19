<template>
  <div class="post-card">
    <h3>{{ props.title }}</h3>
    <p>{{ props.content }} {{ props.size }}</p>
    <button @click="handleClick">Say Hi</button>
    <PostButton />
  </div>
</template>

<script lang="ts" setup>
import { defineProps, defineEmits } from 'vue';
import PostButton from './PostButton.vue';

const props = defineProps({
  title: String,
  content: String,
  size: Number,
});

const emit = defineEmits(['sayHi']);

const handleClick = () => {
  emit('sayHi', 'Hiiiiiiiiiiiiii');
};
</script>

<style scoped>
.post-card {
  border-radius: 15px;
  padding: 10px;
  margin: 5px;
  border: 1px solid #ccc;
}
</style>
