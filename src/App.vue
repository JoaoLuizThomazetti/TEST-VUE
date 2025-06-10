<script setup lang="ts">
import customCard from './components/customCard.vue';

const products = Array.from({ length: 5 }, (_, i) => ({
  name: `Product ${i + 1}`,
  code: `P00${i + 1}`
}));

</script>

<template>
  <header>Testing VUE</header>
  <customCard v-for="(product, index) in products" :key="index" :product="product" />
</template>

<style scoped>
</style>
