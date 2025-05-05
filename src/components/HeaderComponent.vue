<template>
  <div>
    <!-- Navbar -->
    <div class="h-24 flex justify-between px-8 lg:px-20 py-6 bg-gradient-to-r from-blue-800 via-blue-900 to-slate-900 shadow-lg items-center">
      <!-- Logo -->
      <div>
        <img src="/myworld.png" height="150" width="150" alt="myworld Image"
          class="mr-2 transform hover:scale-105 transition-all duration-300" />
      </div>

      <!-- Desktop Links -->
      <ul class="hidden lg:flex justify-end space-x-8 text-white">
        <li v-for="(link, index) in links" :key="index">
          <router-link
            :to="link.route"
            class="text-lg font-semibold hover:text-white transition-colors duration-300 transform hover:scale-110"
          >
            {{ link.text }}
          </router-link>
        </li>
      </ul>

      <!-- Mobile Menu Button -->
      <button @click="toggleMenu" class="lg:hidden text-white focus:outline-none">
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>

    <!-- Mobile Menu Dropdown -->
    <div v-if="isMenuOpen" class="lg:hidden bg-gradient-to-r from-blue-800 via-blue-900 to-slate-900 text-white px-8 py-4 shadow-md">
      <ul class="space-y-4">
        <li v-for="(link, index) in links" :key="index">
          <router-link
            @click="toggleMenu"
            :to="link.route"
            class="block text-lg font-semibold hover:text-blue-300 transition-colors duration-300"
          >
            {{ link.text }}
          </router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

// Example links data
const links = [
  { text: 'Home', route: '/' },
  { text: 'About', route: '/about' },
  { text: 'Services', route: '/services' },
  { text: 'Contact', route: '/contact' },
]
</script>

  
  <style scoped>
  /* Custom Gradient Background */

  ul li a {
    transition: all 0.3s ease-in-out;
  }
  
  ul li a:hover {
    text-decoration: underline;
  }
  </style>
  