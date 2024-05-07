<script setup lang="ts">

</script>

<template>
  <header class="app-header-wrapper p-2 bg-green-400 flex items-center fixed top-0 w-full gap-2">
    <div class="flex-1 flex items-center gap-2">
      <Icon name="simple-icons:burgerking" color="white" size="2rem" />
      <h1 class="text-white text-xl font-bold">
          Burger
      </h1>
    </div>
    <nav>
      <ul class="flex gap-2">
        <li>
          <button>
            <Icon name="mdi:cart" color="white" size="2rem" />
          </button>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.app-header-wrapper {
  height: 60px;
}
</style>