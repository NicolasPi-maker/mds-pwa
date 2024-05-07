<script setup lang="ts">
 const navItems = [
    {
      title: 'Menu',
      icon: 'mdi:hamburger',
      name: 'index'
    },
    {
      title: 'Commande',
      icon: 'material-symbols:order-approve-outline-sharp',
      name: 'bill'
    },
    {
      title: 'Contact',
      icon: 'material-symbols:mail-outline-rounded',
      name: 'contact'
    }
  ]
</script>

<template>
  <div class="app-header-wrapper p-2 bg-green-400 flex items-center fixed bottom-0 w-full">
   <ul class="flex justify-around w-full">
     <nuxt-link v-for="item in navItems" :key="item.title" :to="{name: item.name}" class="flex items-center gap-2">
       <Icon :name="item.icon" color="white" size="3rem" />
    </nuxt-link>
   </ul>
  </div>
</template>

<style scoped>
.app-header-wrapper {
  height: 80px;
}
</style>