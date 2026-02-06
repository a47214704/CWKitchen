<template>
  <div class="flex-col">

    <main class="flex-grow pt-32 pb-24">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16 fade-up-hidden observer-target">
          <h1 class="text-4xl font-serif text-stone-800 mb-4">Our Menu</h1>
          <p class="text-stone-500 font-light tracking-wide">Discover our handcrafted selection</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-8 gap-y-16">
          <div v-for="(product, index) in products" :key="product.id" class="fade-up-hidden observer-target"
            :class="`delay-${index * 100}`">
            <ProductCard v-bind="product" @click="openLink()" />
          </div>
        </div>
      </div>
    </main>

  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
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

// Intersection Observer for scroll animations
onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('fade-up-visible')
        entry.target.classList.remove('fade-up-hidden')
        observer.unobserve(entry.target)
      }
    })
  }, {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  })

  document.querySelectorAll('.observer-target').forEach((el) => {
    observer.observe(el)
  })
})
</script>
