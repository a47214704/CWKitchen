<template>
  <div class="group cursor-pointer">
    <div class="relative overflow-hidden aspect-square bg-stone-50 mb-4">
      <img 
        :src="image" 
        :alt="name"
        class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700 ease-out"
      >
      <div class="absolute inset-0 bg-black/5 group-hover:bg-transparent transition-colors duration-300"></div>
    </div>
    <div class="text-center space-y-2">
      <h3 class="text-xl font-serif text-stone-800 tracking-wide">{{ name }}</h3>
      <p class="text-milk-yellow-600 font-medium tracking-widest">{{ price }}</p>
      <p class="text-stone-500 text-sm font-light line-clamp-2 px-4">{{ description }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  name: string
  price: string
  description: string
  image: string
}>()
</script>
