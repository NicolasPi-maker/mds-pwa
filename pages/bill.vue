<script setup lang="ts">
const cart = useState('cart', () => {
  return {
    items: []
  }
});
</script>

<template>
  {{ cart }}
  <div v-for="item in cart" :key="item.id" class="flex gap-2 m-3">
    <h2 class="flex-1 font-bold text-gray-700 text-xl">{{ item.name }}</h2>
    <h2 class="text-gray-700 text-xl">{{ item.price / 10 }} €</h2>
  </div>
</template>

<style scoped>

</style>