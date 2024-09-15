<template>
  <div class="post-card">
    <h3>Tittle</h3>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nam exercitationem aspernatur maxime velit voluptatum voluptates non inventore numquam, aliquid veritatis obcaecati, iure, quod dignissimos libero quae perspiciatis neque? Voluptas.</p>
    <PostButton />
  </div>
</template>

<script lang="ts" setup>
import PostButton from './PostButton.vue';
</script>

<style scoped>
.post-card {
  border-radius: 15px;
  padding: 10px;
  margin: 5px;
  border: 1px solid #ccc;
}
</style>
