<template>
  <button @click="addCounter" class="post-btn">
    Counter <span>{{ counter }}</span>
  </button>

  <h3 :class="{ danger: counter > 5 }" v-if="counter > 5">Es Mayor de edad</h3>
  <h3 v-else>Es Menor de edad</h3>

  <ul>
    <li :class="{ danger: country.name.length > 5 }" v-for="country in countries" :key="country.name">{{ country.name }}</li>
  </ul>

  <input type="text" v-model="nombreInput" />
  <p>{{ nombreInput }}</p>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';
let counter: Ref = ref(0);
const addCounter = (): number => counter.value++;

interface ICountry {
  name: string;
}

let countries: Ref<Array<ICountry>> = ref([{ name: 'Spain' }, { name: 'France' }, { name: 'UK' }, { name: 'Italy' }, { name: 'Portugal' }]);

let nombreInput: Ref<string> = ref('');
</script>

<style scoped>
.post-btn {
  padding: 15px;
  background-color: blueviolet;
  color: white;
  border: 1px solid transparent;
  outline: 0;
  cursor: pointer;
  text-transform: uppercase;
}
.post-btn:hover {
  background-color: white;
  color: blueviolet;
  border: 1px solid blueviolet;
}
.danger {
  color: red;
}
</style>
