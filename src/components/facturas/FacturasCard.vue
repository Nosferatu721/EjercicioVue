<template>
  <div class="card-facturas">
    <div class="item">
      <p>- Order:</p>
      <span>{{ props.orderCode }}</span>
    </div>
    <div class="item">
      <p>- Cantidad Productos:</p>
      <span>{{ props.countProducts }}</span>
    </div>
    <div class="item">
      <p>- Subtotal:</p>
      <span>{{ props.valor }}</span>
    </div>
    <div class="item">
      <p>- IVA:</p>
      <span>{{ ivaSubtotal }}</span>
    </div>
    <hr />
    <div>- Total: {{ total }}</div>
  </div>
</template>

<script lang="ts" setup>
import { defineProps, computed, Ref } from 'vue';

const IVA = 19;
const props = defineProps({
  orderCode: Number,
  valor: Number,
  countProducts: Number,
});

const ivaSubtotal = computed(() => (props.valor ? props.valor * (IVA / 100) : 0));
const total = computed(() => (props.valor ? props.valor + ivaSubtotal.value : 0));
</script>

<style scoped>
.card-facturas {
  background-color: rgb(241, 241, 241);
  padding: 20px;
  border-radius: 10px;
  margin: 10px;
}
.card-facturas .item {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
</style>
