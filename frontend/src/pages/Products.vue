<template>
  <div class="flex-col">
    
    <main class="flex-grow pt-12 pb-24">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h1 class="text-4xl font-serif text-stone-800 mb-4">Our Menu</h1>
          <p class="text-stone-500 font-light tracking-wide">Discover our handcrafted selection</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-8 gap-y-16">
          <ProductCard 
            v-for="product in products" 
            :key="product.id"
            v-bind="product"
          />
        </div>
      </div>
    </main>

  </div>
</template>

<script setup lang="ts">

import ProductCard from '../components/ProductCard.vue'

const products = [
  {
    id: 1,
    name: "Classic Tiramisu",
    price: "NT$ 180",
    description: "Our signature dessert. Espresso-dipped ladyfingers layered with a light and airy mascarpone cream, finished with premium cocoa powder.",
    image: "/images/tiramisu.png"
  },
  {
    id: 2,
    name: "Bordeaux Canelé",
    price: "NT$ 85",
    description: "A masterpiece of texture. Crunchy caramelized exterior giving way to a soft, custardy interior with hints of vanilla and rum.",
    image: "/images/canele.png"
  },
  {
    id: 3,
    name: "Matcha Tiramisu",
    price: "NT$ 190",
    description: "A Japanese twist on the classic. Premium Uji matcha powder layered with creamy mascarpone.",
    image: "/images/tiramisu.png"  // Reusing image for demo
  },
  {
    id: 4,
    name: "Canelé Box Set (6pcs)",
    price: "NT$ 480",
    description: "Share the joy with a box of 6 freshly baked canelés. Perfect for gifting or gatherings.",
    image: "/images/canele.png" // Reusing image for demo
  },
  {
    id: 5,
    name: "Afternoon Tea Set",
    price: "NT$ 650",
    description: "A curated selection including 2 Tiramisu cups and 4 Canelés.",
    image: "/images/hero-1.png"
  }
]
</script>
