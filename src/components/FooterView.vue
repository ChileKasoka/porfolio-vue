<template>
  <footer class="bg-gray-900 text-gray-200 py-8 font-coder">
    <div class="container mx-auto px-4 flex flex-col md:flex-row justify-between items-center">
      <!-- Branding -->
      <div class="mb-4 md:mb-0 text-center md:text-left">
        <img src="/public/ck.png" alt="Logo" class="w-32 h-32">
        <p class="text-sm text-gray-400">&copy; {{ currentDate }} All rights reserved</p>
      </div>

      <!-- Quick Links -->
      <div class="mb-4 md:mb-0">
        <h3 class="font-semibold mb-2">Quick Links</h3>
        <ul class="space-y-1 text-gray-400">
          <li><a href="/#about" class="hover:text-white">About Me</a></li>
          <li><a href="/#projects" class="hover:text-white">Projects</a></li>
          <li><a href="/#contact" class="hover:text-white">Contact</a></li>
          <li><a href="/cv.pdf" download class="hover:text-white">Download CV</a></li>
          <li><a href="/certificates.pdf" download class="hover:text-white">Certificates</a></li>
        </ul>
      </div>

      <!-- Social Links -->
      <div class="text-center md:text-right">
        <h3 class="font-semibold mb-2">Connect with me</h3>
        <div class="flex justify-center md:justify-end space-x-4">
          <a href="https://linkedin.com/in/ckayzy" target="_blank" class="hover:text-blue-500">LinkedIn</a>
          <a href="https://github.com/ckayzy" target="_blank" class="hover:text-gray-100">GitHub</a>
          <a href="https://twitter.com/ckayzy" target="_blank" class="hover:text-blue-400">Twitter</a>
          <a href="mailto:ckayzy@example.com" class="hover:text-red-400">Email</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const currentDate = new Date().getFullYear();
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

.font-coder {
  font-family: 'Press Start 2P', cursive;
}
</style>
