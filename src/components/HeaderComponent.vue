<template>
  <div class="fixed top-0 w-full z-50">

    <!-- NAVBAR -->
    <div
      :class="[
        'transition-all duration-500',
        isScrolled
          ? 'bg-[#0b0f19]/80 backdrop-blur-xl border-b border-white/10 shadow-lg'
          : 'bg-transparent'
      ]"
      class="flex justify-between items-center px-6 lg:px-20 py-5"
    >

      <!-- LOGO -->
      <div class="text-2xl font-extrabold tracking-wide cursor-pointer group">
        <span class="bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
          $ ck
        </span>
      </div>

      <!-- DESKTOP LINKS -->
      <ul class="hidden lg:flex items-center space-x-10">
        <li v-for="(link, index) in links" :key="index" class="relative group">

          <a
            :href="link.href"
            @click.prevent="scrollToSection(link.href)"
            class="text-sm font-semibold tracking-wide text-gray-300 hover:text-white transition"
          >
            {{ link.text }}
          </a>

          <!-- animated underline -->
          <span
            class="absolute left-0 -bottom-1 w-0 h-[2px] bg-gradient-to-r from-cyan-400 to-purple-500 transition-all duration-300 group-hover:w-full"
          ></span>

        </li>
      </ul>

      <!-- MOBILE BUTTON -->
      <button
        @click="toggleMenu"
        class="lg:hidden text-white focus:outline-none"
      >
        <svg
          v-if="!isMenuOpen"
          class="w-8 h-8"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16" />
        </svg>

        <!-- CLOSE ICON -->
        <svg
          v-else
          class="w-8 h-8"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>

    <!-- MOBILE MENU -->
    <transition name="fade">
      <div
        v-if="isMenuOpen"
        class="lg:hidden bg-[#0b0f19]/95 backdrop-blur-xl border-t border-white/10 px-6 py-8"
      >
        <ul class="space-y-6 text-center">

          <li v-for="(link, index) in links" :key="index">
            <a
              :href="link.href"
              @click="scrollToSection(link.href); toggleMenu()"
              class="block text-lg font-semibold text-gray-300 hover:text-cyan-400 transition"
            >
              {{ link.text }}
            </a>
          </li>

        </ul>
      </div>
    </transition>

  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isMenuOpen = ref(false)
const isScrolled = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const links = [
  { text: 'Home', href: '#home' },
  { text: 'About', href: '#about' },
  { text: 'Projects', href: '#projects' },
  { text: 'Services', href: '#services' },
  { text: 'Contact', href: '#contact' },
]

// Smooth scroll
const scrollToSection = (hash) => {
  const el = document.querySelector(hash)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
  }
}

// Detect scroll (for blur navbar effect)
const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style>
/* Mobile animation */
.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from {
  opacity: 0;
  transform: translateY(-10px);
}
.fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>