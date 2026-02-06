<template>
  <div class="relative h-screen w-full overflow-hidden">
    <n-carousel autoplay show-arrow>
      <div v-for="(slide, index) in slides" :key="index" class="relative h-screen w-full">
        <img :src="slide.image" class="w-full h-full object-cover" :alt="slide.title">
        <div class="absolute inset-0 bg-black/20 flex items-center justify-center">
          <div class="text-center text-white space-y-4">
            <h2 class="text-5xl font-serif font-bold tracking-widest drop-shadow-md animate-hero animate-hero-title">{{
              slide.title }}</h2>
            <p class="text-xl tracking-wider font-light drop-shadow-sm animate-hero animate-hero-subtitle">{{
              slide.subtitle }}</p>
            <div class="animate-hero animate-hero-button">
              <router-link to="/products"
                class="inline-block mt-8 px-8 py-3 bg-white/90 hover:bg-white text-stone-800 tracking-widest font-medium transition-all duration-300 backdrop-blur-sm">
                EXPLORE
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </n-carousel>
  </div>
</template>

<script setup lang="ts">
import { NCarousel } from 'naive-ui'

const slides = [
  {
    image: '/images/hero-1.png',
    title: 'SWEET ELEGANCE',
    subtitle: 'Handcrafted Desserts for Special Moments'
  },
  {
    image: '/images/tiramisu.png',
    title: 'CLASSIC TIRAMISU',
    subtitle: 'The Authentic Taste of Italy'
  }
]
</script>

<style scoped>
:deep(.n-carousel__arrow) {
  background-color: rgba(255, 255, 255, 0.2);
  color: white;
}

:deep(.n-carousel__arrow:hover) {
  background-color: rgba(255, 255, 255, 0.4);
}

:deep(.n-carousel__dots) {
  bottom: 24px;
}

:deep(.n-carousel__dot--active) {
  background-color: white;
}
</style>
