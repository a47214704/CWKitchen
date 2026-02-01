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
            @click="openLink()"
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
    name: "經典義式提拉米蘇",
    price: "NT$ 130",
    description: "Our signature dessert. Espresso-dipped ladyfingers layered with a light and airy mascarpone cream, finished with premium cocoa powder.",
    image: "/images/提拉米蘇.jpg"
  },
  {
    id: 2,
    name: "法式可麗露",
    price: "NT$ 60",
    description: "A masterpiece of texture. Crunchy caramelized exterior giving way to a soft, custardy interior with hints of vanilla and rum.",
    image: "/images/可麗露.jpg"
  }
]

function openLink() {
  window.open('https://myship.7-11.com.tw/general/detail?id=GM2602013174313', '_blank')
}
</script>
