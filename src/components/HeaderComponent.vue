<template>
  <div class="w-full sticky top-0 z-50">
    <!-- Navbar -->
    <div class="h-16 flex justify-between px-8 lg:px-20 py-6 shadow-lg items-center bg-slate-50">
      <!-- Logo -->
      <div class="text-black text-2xl font-bold">
        $ ck
      </div>

      <!-- Desktop Links -->
      <ul class="hidden lg:flex justify-end space-x-8 text-slate-700">
        <li v-for="(link, index) in links" :key="index">
          <a
            :href="link.href"
            class="text-lg font-semibold hover:text-slate-500 transition-colors duration-300 transform hover:scale-110"
            @click.prevent="scrollToSection(link.href)"
          >
            {{ link.text }}
          </a>
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
          <a
            @click="scrollToSection(link.href); toggleMenu()"
            :href="link.href"
            class="block text-lg font-semibold hover:text-blue-300 transition-colors duration-300"
          >
            {{ link.text }}
          </a>
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

// Update links for same-page anchor navigation
const links = [
  { text: 'Home', href: '#home' },
  { text: 'About', href: '#about' },
  { text: 'Projects', href: '#projects' },
  { text: 'Services', href: '#services' },
  { text: 'Contact', href: '#contact' },
]

// Smooth scroll function
const scrollToSection = (hash) => {
  const element = document.querySelector(hash)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>
