<template>
  <div class="post-card">
    <h3>{{ props.title }}</h3>
    <p>{{ props.content }} {{ props.size }}</p>
    <button @click="handleClick">Say Hi</button>
    <PostButton />
  </div>
</template>

<script lang="ts">
// import PostButton from './PostButton.vue';
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'PostCard',
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      required: false,
      default: 'No tiene contenido ***',
    },
    size: {
      type: Number,
      required: false,
      default: 0,
    },
  },
  emits: ['sayHi'],
  setup(props, { emit }) {
    const handleClick = () => {
      emit('sayHi', 'Hiiiiiiiiiiiiii');
    };
    return { props, handleClick};
  },
});
</script>

<style scoped>
.post-card {
  border-radius: 15px;
  padding: 10px;
  margin: 5px;
  border: 1px solid #ccc;
}
</style>
