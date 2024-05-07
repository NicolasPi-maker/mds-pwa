<script setup lang="ts">
import burgers from '~/data/burgers.json';
import FoodCard from "~/components/FoodCard.vue";
</script>

<template>
  <FoodCard v-for="burger in burgers" :key="burger.id" :burger="burger" />
</template>

<style scoped>

</style>