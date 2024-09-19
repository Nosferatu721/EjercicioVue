<template>
  <h3>Facturas</h3>
  <FacturasCard v-for="(fact, i) in facturas" :key="i" :orderCode="fact.orderCode" :valor="fact.valor" :countProducts="fact.countProducts" />
</template>

<script lang="ts" setup>
import FacturasCard from './FacturasCard.vue';

interface IFactura {
  orderCode: number;
  valor: number;
  countProducts: number;
}

let facturas: Array<IFactura> = [
  {
    orderCode: 324874,
    valor: 0,
    countProducts: 2,
  },
  {
    orderCode: 324874,
    valor: 25000,
    countProducts: 2,
  },
  {
    orderCode: 564986,
    valor: 100000,
    countProducts: 8,
  },
  {
    orderCode: 994844,
    valor: 562000,
    countProducts: 5,
  },
];
</script>

<style scoped></style>
