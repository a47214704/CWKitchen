<template>
  <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-milk-yellow/50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-20 items-center">
        <!-- Logo -->
        <div class="flex-shrink-0 flex items-center space-x-3">
          <img src="/logo.jpg" alt="C.W Kitchen Logo" class="h-12 w-12 rounded-full object-cover">
          <router-link to="/" class="text-2xl font-serif font-bold text-stone-800 tracking-widest hidden sm:block">
            C.W KITCHEN
          </router-link>
          <router-link to="/" class="text-xl font-serif font-bold text-stone-800 tracking-widest sm:hidden">
            C.W
          </router-link>
        </div>
        
        <!-- Desktop Menu -->
        <div class="hidden sm:flex space-x-12">
          <router-link to="/" class="text-stone-600 hover:text-stone-900 transition-colors uppercase tracking-widest text-sm font-medium">Home</router-link>
          <router-link to="/products" class="text-stone-600 hover:text-stone-900 transition-colors uppercase tracking-widest text-sm font-medium">Products</router-link>
        </div>

        <!-- Mobile Menu Button -->
        <div class="sm:hidden flex items-center z-50">
          <button @click="isMenuOpen = !isMenuOpen" class="text-stone-600 p-2 focus:outline-none">
            <div class="w-6 h-6 flex flex-col justify-center items-end space-y-1.5 transition-all duration-300">
              <span :class="{'rotate-45 translate-y-2': isMenuOpen}" class="block h-0.5 w-6 bg-current transform transition-transform duration-300"></span>
              <span :class="{'opacity-0': isMenuOpen}" class="block h-0.5 w-4 bg-current transition-opacity duration-300"></span>
              <span :class="{'-rotate-45 -translate-y-2 w-6': isMenuOpen}" class="block h-0.5 w-5 bg-current transform transition-all duration-300"></span>
            </div>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu Overlay -->
    <Teleport to="body">
      <Transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="isMenuOpen" class="fixed inset-0 z-40 bg-stone-900/30 backdrop-blur-sm" @click="isMenuOpen = false"></div>
      </Transition>

      <Transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="-translate-y-full opacity-0"
        enter-to-class="translate-y-0 opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="translate-y-0 opacity-100"
        leave-to-class="-translate-y-full opacity-0"
      >
        <div v-if="isMenuOpen" class="fixed top-0 left-0 w-full z-40 bg-white shadow-xl border-b border-stone-100 pt-24 pb-8 px-6 sm:hidden">
          <div class="flex flex-col space-y-6 text-center">
            <router-link 
              to="/" 
              class="text-xl font-serif text-stone-800 hover:text-stone-600 transition-colors tracking-widest"
              @click="isMenuOpen = false"
            >
              HOME
            </router-link>
            <router-link 
              to="/products" 
              class="text-xl font-serif text-stone-800 hover:text-stone-600 transition-colors tracking-widest"
              @click="isMenuOpen = false"
            >
              PRODUCTS
            </router-link>
          </div>
        </div>
      </Transition>
    </Teleport>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)
</script>
