<script setup lang="ts">
defineProps({
  burger: {
    type: Object,
    required: true
  }
});
const cart = useState('cart', () => []);

const addToCart = (burger) => {
  cart.value.push(burger);
  localStorage.setItem('cart', JSON.stringify(cart.value));
}
</script>

<template>
  <div class="flex flex-col justify-center m-3">
    <NuxtImg :src="burger.img" :alt="burger.name" />
    <h1 class="text-gray-700 text-xl font-bold">
      {{ burger.name }}
    </h1>
    <button @click="addToCart(burger)" class="p-2 bg-green-400 rounded text-white">Ajouter</button>
  </div>
</template>

<style scoped>

</style>