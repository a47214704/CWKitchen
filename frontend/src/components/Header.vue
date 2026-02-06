<template>
  <nav class="fixed top-0 w-full z-50 transition-all duration-300" :class="headerBgClass">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center transition-all duration-300">
        <!-- Logo Text Only (No Image) -->
        <div class="flex-shrink-0 flex items-center">
          <router-link to="/" class="text-2xl font-serif font-bold tracking-[0.2em] transition-colors duration-300"
            :class="textColorClass">
            C.W KITCHEN
          </router-link>
        </div>

        <!-- Desktop Menu -->
        <div class="hidden sm:flex space-x-12">
          <router-link v-for="link in links" :key="link.path" :to="link.path" @click="scrollToTop()"
            class="text-sm font-medium uppercase tracking-[0.15em] transition-colors duration-300 hover:opacity-70"
            :class="linkColorClass">
            {{ link.name }}
          </router-link>
        </div>

        <!-- Mobile Menu Button -->
        <div class="sm:hidden flex items-center z-50">
          <button @click="isMenuOpen = !isMenuOpen" class="p-2 focus:outline-none transition-colors"
            :class="mobileButtonColorClass">
            <div class="w-6 h-6 flex flex-col justify-center items-end space-y-1.5 transition-all duration-300">
              <span :class="{ 'rotate-45 translate-y-2': isMenuOpen }"
                class="block h-0.5 w-6 bg-current transform transition-transform duration-300"></span>
              <span :class="{ 'opacity-0': isMenuOpen }"
                class="block h-0.5 w-4 bg-current transition-opacity duration-300"></span>
              <span :class="{ '-rotate-45 -translate-y-2 w-6': isMenuOpen }"
                class="block h-0.5 w-5 bg-current transform transition-all duration-300"></span>
            </div>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu Overlay -->
    <Teleport to="body">
      <Transition enter-active-class="transition duration-300 ease-out" enter-from-class="opacity-0"
        enter-to-class="opacity-100" leave-active-class="transition duration-200 ease-in" leave-from-class="opacity-100"
        leave-to-class="opacity-0">
        <div v-if="isMenuOpen" class="fixed inset-0 z-40 bg-stone-900/30 backdrop-blur-sm" @click="isMenuOpen = false">
        </div>
      </Transition>

      <Transition enter-active-class="transition duration-300 ease-out" enter-from-class="-translate-y-full opacity-0"
        enter-to-class="translate-y-0 opacity-100" leave-active-class="transition duration-200 ease-in"
        leave-from-class="translate-y-0 opacity-100" leave-to-class="-translate-y-full opacity-0">
        <div v-if="isMenuOpen" class="fixed top-0 left-0 w-full z-40 bg-white shadow-xl pt-24 pb-12 px-8 sm:hidden">
          <div class="flex flex-col space-y-8 text-center">
            <router-link v-for="link in links" :key="link.path" :to="link.path"
              class="text-xl font-serif text-stone-900 hover:text-stone-600 transition-colors tracking-widest font-semibold"
              @click="isMenuOpen = false; scrollToTop()">
              {{ link.name }}
            </router-link>
          </div>
        </div>
      </Transition>
    </Teleport>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const isMenuOpen = ref(false)
const isScrolled = ref(false)

const links = [
  { name: 'Home', path: '/' },
  { name: 'Products', path: '/products' }
]

// Check if current page is home page
const isHomePage = computed(() => route.path === '/')

// Header background classes - only transparent on home page
const headerBgClass = computed(() => {
  if (isHomePage.value) {
    // Home page: transparent -> white on scroll
    return isScrolled.value ? 'bg-white/90 backdrop-blur-md shadow-sm py-2' : 'bg-transparent py-4'
  } else {
    // Other pages: always white
    return 'bg-white/90 backdrop-blur-md shadow-sm py-2'
  }
})

// Text color - white on transparent, dark on white background
const textColorClass = computed(() => {
  if (isHomePage.value && !isScrolled.value && !isMenuOpen.value) {
    return 'text-white drop-shadow-md'
  } else {
    return 'text-stone-800'
  }
})

// Menu link color
const linkColorClass = computed(() => {
  if (isHomePage.value && !isScrolled.value) {
    return 'text-white hover:text-white/80 drop-shadow-sm'
  } else {
    return 'text-stone-600 hover:text-stone-900'
  }
})

// Mobile button color
const mobileButtonColorClass = computed(() => {
  if (isHomePage.value && !isScrolled.value && !isMenuOpen.value) {
    return 'text-white'
  } else {
    return 'text-stone-600'
  }
})

function handleScroll() {
  isScrolled.value = window.scrollY > 50
}

function scrollToTop() {
  window.scrollTo(0, 0)
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
