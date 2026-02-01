<template>
  <div class="flex-col">
    
    <main class="flex-grow">
      <!-- Hero Section -->
      <HeroCarousel />

      <!-- About Section -->
      <section class="py-24 px-4 bg-milk-yellow/10">
        <div class="max-w-4xl mx-auto text-center space-y-8">
          <span class="text-sm uppercase tracking-[0.2em] text-stone-500">Our Story</span>
          <h2 class="text-4xl font-serif text-stone-800 leading-tight">
            Crafting Sweet Memories<br>
            One Dessert at a Time
          </h2>
          <p class="text-stone-600 leading-relaxed font-light text-lg">
            At C.W Kitchen, we believe that every dessert tells a story. From our signature Tiramisu to our perfectly baked Canelé, each creation is a masterpiece of flavor and texture, made with the finest ingredients and a passion for perfection.
          </p>
        </div>
      </section>

      <!-- Featured Products Preview -->
      <section class="py-24 px-4 max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-serif text-stone-800 mb-4">Featured Collections</h2>
          <div class="w-16 h-0.5 bg-milk-yellow mx-auto"></div>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12">
          <ProductCard 
            v-for="product in featuredProducts" 
            :key="product.id"
            v-bind="product"
            @click="openLink()"
          />
        </div>

        <div class="text-center mt-16">
          <router-link 
            to="/products" 
            class="inline-block border-b border-stone-800 pb-1 text-stone-800 hover:text-stone-500 hover:border-stone-500 transition-colors uppercase tracking-widest text-sm"
          >
            View All Products
          </router-link>
        </div>
      </section>
    </main>

  </div>
</template>

<script setup lang="ts">

import HeroCarousel from '../components/HeroCarousel.vue'
import ProductCard from '../components/ProductCard.vue'

const featuredProducts = [
  {
    id: 1,
    name: "經典義式提拉米蘇",
    price: "NT$ 130",
    description: "Layers of coffee-soaked ladyfingers and mascarpone cream, dusted with cocoa.",
    image: "/images/提拉米蘇.jpg"
  },
  {
    id: 2,
    name: "法式可麗露",
    price: "NT$ 60",
    description: "Traditional French pastry with a caramelized crust and tender custard center.",
    image: "/images/可麗露.jpg"
  }
]

function openLink() {
  window.open('https://myship.7-11.com.tw/general/detail?id=GM2602013174313', '_blank')
}
</script>
