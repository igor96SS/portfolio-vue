<script setup>
import { ref, watch } from 'vue'
import { useRoute } from 'vue-router'

const isMobileMenuOpen = ref(false) // mobile menu state
const route = useRoute()

// Watch for route changes to close the mobile menu
watch(() => route.fullPath, () => {
  isMobileMenuOpen.value = false
})

const isActiveLink = (routePath) => {
  const route = useRoute();
  return route.path === routePath;
}

</script>

<template>
  <nav class="bg-white dark:bg-gray-900 text-white px-6 py-4 shadow-md">
    <div class="container mx-auto flex justify-between items-center">
      <!-- Logo -->
      <RouterLink to="/" class="flex items-center space-x-3">
        <img class="h-10 w-auto" :src="logo" alt="logo" />
        <span class="text-2xl font-bold hidden md:inline">name</span>
      </RouterLink>

      <!-- Navigation Links (Desktop) -->
      <div class="hidden md:flex space-x-6">
        <RouterLink
          to="/"
          :class="[isActiveLink('/') ? 'text-blue-400 border-b-2 border-blue-500' : 'hover:text-blue-400', 'transition-colors font-medium']"
        >
          Home
        </RouterLink>

        <RouterLink
          to="/projects"
          :class="[isActiveLink('/projects') ? 'text-blue-400 border-b-2 border-blue-500' : 'hover:text-blue-400', 'transition-colors font-medium']"
        >
          Projects
        </RouterLink>

        <RouterLink
          to="/about"
          :class="[isActiveLink('/about') ? 'text-blue-400 border-b-2 border-blue-500' : 'hover:text-blue-400', 'transition-colors font-medium']"
        >
          About
        </RouterLink>

        <RouterLink
          to="/contact"
          :class="[isActiveLink('/contact') ? 'text-blue-400 border-b-2 border-blue-500' : 'hover:text-blue-400', 'transition-colors font-medium']"
        >
          Contact
        </RouterLink>
      </div>

      <!-- Mobile hamburger button -->
      <button
        class="md:hidden text-blue-100 hover:text-blue-400 transition-colors"
        @click="isMobileMenuOpen = !isMobileMenuOpen"
      >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
      </svg>

      </button>
    </div>

    <!-- Mobile Nav Menu -->
    <div v-show="isMobileMenuOpen" class="md:hidden px-4 pb-4 space-y-2">
      <RouterLink 
        to="/"
        :class="[isActiveLink('/') ? 'text-blue-400 border-b inline-block border-blue-500' : 'hover:text-blue-400', 'block']"
        @click="isMobileMenuOpen = false"
      >
        Home
      </RouterLink>
      <RouterLink 
        to="/projects"
        :class="[isActiveLink('/projects') ? 'text-blue-400 border-b inline-block border-blue-500' : 'hover:text-blue-400', 'block']"
        @click="isMobileMenuOpen = false"
      >
        Projects
      </RouterLink>
      <RouterLink 
        to="/about"
        :class="[isActiveLink('/about') ? 'text-blue-400 border-b inline-block border-blue-500' : 'hover:text-blue-400', 'block']"
        @click="isMobileMenuOpen = false"
      >
        About
      </RouterLink>
      <RouterLink 
        to="/contact"
        :class="[isActiveLink('/contact') ? 'text-blue-400 border-b inline-block border-blue-500' : 'hover:text-blue-400', 'block']"
        @click="isMobileMenuOpen = false"
      >
        Contact
      </RouterLink>
    </div>
  </nav>
</template>