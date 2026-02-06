<template>
  <div class="flex-col">

    <main class="flex-grow">
      <!-- Hero Section -->
      <HeroCarousel />

      <!-- Why Choose Us Section (Enhanced) -->
      <section class="py-32 px-4 bg-gradient-to-b from-white via-stone-50 to-white relative overflow-hidden">
        <!-- Decorative Background -->
        <div class="absolute inset-0 opacity-30">
          <div class="absolute top-20 left-10 w-64 h-64 bg-milk-yellow/20 rounded-full blur-3xl"></div>
          <div class="absolute bottom-20 right-10 w-96 h-96 bg-stone-200/30 rounded-full blur-3xl"></div>
        </div>

        <div class="max-w-7xl mx-auto relative z-10">
          <!-- Section Title -->
          <div class="text-center mb-20 fade-up-hidden observer-target">
            <span class="text-sm uppercase tracking-[0.25em] text-stone-500 font-medium">Why Choose Us</span>
            <h2 class="text-4xl md:text-5xl font-serif text-stone-800 mt-4 tracking-wide">Our Promise to You</h2>
            <div class="w-24 h-1 bg-gradient-to-r from-transparent via-milk-yellow to-transparent mx-auto mt-6"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-12 lg:gap-16">

            <!-- Item 1: Premium Quality -->
            <div class="group fade-up-hidden observer-target delay-200">
              <div
                class="bg-white rounded-2xl p-10 shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 border border-stone-100">
                <!-- Icon Container -->
                <div class="w-24 h-24 mx-auto mb-8 relative">
                  <div
                    class="absolute inset-0 bg-gradient-to-br from-amber-100 to-milk-yellow rounded-2xl transform rotate-6 group-hover:rotate-12 transition-transform duration-300">
                  </div>
                  <div class="absolute inset-0 bg-white rounded-2xl shadow-md flex items-center justify-center">
                    <!-- Premium Quality SVG Icon -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-12 h-12 text-amber-600" fill="none"
                      viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                      <path stroke-linecap="round" stroke-linejoin="round"
                        d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
                    </svg>
                  </div>
                </div>

                <h3 class="text-2xl font-serif text-stone-800 tracking-wide text-center mb-4">Premium Quality</h3>
                <p class="text-stone-600 leading-relaxed text-center font-light">
                  Sourced from the finest local farms and premium global suppliers to ensure every bite is perfection.
                </p>
              </div>
            </div>

            <!-- Item 2: Handcrafted with Love -->
            <div class="group fade-up-hidden observer-target delay-400">
              <div
                class="bg-white rounded-2xl p-10 shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 border border-stone-100">
                <!-- Icon Container -->
                <div class="w-24 h-24 mx-auto mb-8 relative">
                  <div
                    class="absolute inset-0 bg-gradient-to-br from-rose-100 to-pink-100 rounded-2xl transform rotate-6 group-hover:rotate-12 transition-transform duration-300">
                  </div>
                  <div class="absolute inset-0 bg-white rounded-2xl shadow-md flex items-center justify-center">
                    <!-- Heart/Handmade SVG Icon -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-12 h-12 text-rose-500" fill="currentColor"
                      viewBox="0 0 24 24" stroke="none">
                      <path
                        d="M11.645 20.91l-.007-.003-.022-.012a15.247 15.247 0 01-.383-.218 25.18 25.18 0 01-4.244-3.17C4.688 15.36 2.25 12.174 2.25 8.25 2.25 5.322 4.714 3 7.688 3A5.5 5.5 0 0112 5.052 5.5 5.5 0 0116.313 3c2.973 0 5.437 2.322 5.437 5.25 0 3.925-2.438 7.111-4.739 9.256a25.175 25.175 0 01-4.244 3.17 15.247 15.247 0 01-.383.219l-.022.012-.007.004-.003.001a.752.752 0 01-.704 0l-.003-.001z" />
                    </svg>
                  </div>
                </div>

                <h3 class="text-2xl font-serif text-stone-800 tracking-wide text-center mb-4">Handcrafted with Love</h3>
                <p class="text-stone-600 leading-relaxed text-center font-light">
                  Each dessert is meticulously crafted by our artisanal chefs, pouring passion into every detail.
                </p>
              </div>
            </div>

            <!-- Item 3: Fresh Everyday -->
            <div class="group fade-up-hidden observer-target delay-600">
              <div
                class="bg-white rounded-2xl p-10 shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 border border-stone-100">
                <!-- Icon Container -->
                <div class="w-24 h-24 mx-auto mb-8 relative">
                  <div
                    class="absolute inset-0 bg-gradient-to-br from-emerald-100 to-teal-100 rounded-2xl transform rotate-6 group-hover:rotate-12 transition-transform duration-300">
                  </div>
                  <div class="absolute inset-0 bg-white rounded-2xl shadow-md flex items-center justify-center">
                    <!-- Fresh/Sparkles SVG Icon -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-12 h-12 text-emerald-600" fill="none"
                      viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5">
                      <path stroke-linecap="round" stroke-linejoin="round"
                        d="M9.813 15.904L9 18.75l-.813-2.846a4.5 4.5 0 00-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 003.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 003.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 00-3.09 3.09zM18.259 8.715L18 9.75l-.259-1.035a3.375 3.375 0 00-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 002.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 002.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 00-2.456 2.456zM16.894 20.567L16.5 21.75l-.394-1.183a2.25 2.25 0 00-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 001.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 001.423 1.423l1.183.394-1.183.394a2.25 2.25 0 00-1.423 1.423z" />
                    </svg>
                  </div>
                </div>

                <h3 class="text-2xl font-serif text-stone-800 tracking-wide text-center mb-4">Fresh Everyday</h3>
                <p class="text-stone-600 leading-relaxed text-center font-light">
                  Baked fresh daily to guarantee the ultimate taste experience when it reaches your door.
                </p>
              </div>
            </div>

          </div>
        </div>
      </section>

      <!-- About Section -->
      <section class="py-24 px-4 bg-milk-yellow/10">
        <div class="max-w-4xl mx-auto text-center space-y-8 fade-up-hidden observer-target">
          <span class="text-sm uppercase tracking-[0.2em] text-stone-500">Our Story</span>
          <h2 class="text-4xl font-serif text-stone-800 leading-tight">
            Crafting Sweet Memories<br>
            One Dessert at a Time
          </h2>
          <p class="text-stone-600 leading-relaxed font-light text-lg">
            At C.W Kitchen, we believe that every dessert tells a story. From our signature Tiramisu to our perfectly
            baked Canelé, each creation is a masterpiece of flavor and texture, made with the finest ingredients and a
            passion for perfection.
          </p>
        </div>
      </section>

      <!-- Featured Products Preview -->
      <section class="py-24 px-4 max-w-7xl mx-auto">
        <div class="text-center mb-16 fade-up-hidden observer-target">
          <h2 class="text-3xl font-serif text-stone-800 mb-4">Featured Collections</h2>
          <div class="w-16 h-0.5 bg-milk-yellow mx-auto"></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12">
          <div v-for="(product, index) in featuredProducts" :key="product.id" class="fade-up-hidden observer-target"
            :class="`delay-${index * 100}`">
            <ProductCard v-bind="product" @click="openLink()" />
          </div>
        </div>

        <div class="text-center mt-16 fade-up-hidden observer-target">
          <router-link to="/products"
            class="inline-block border-b border-stone-800 pb-1 text-stone-800 hover:text-stone-500 hover:border-stone-500 transition-colors uppercase tracking-widest text-sm">
            View All Products
          </router-link>
        </div>
      </section>
    </main>

  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
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
