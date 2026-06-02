<template>
  <footer
    class="relative min-h-screen text-gray-200 py-8 font-coder overflow-hidden bg-cover bg-center"
    style="background-image: url('/world.png');"
  >
    <!-- Overlay -->
    <div class="absolute inset-0 bg-[#020617]/70"></div>

    <!-- Content -->
    <div
      class="relative z-10 container mx-auto px-6 min-h-screen flex flex-col md:flex-row justify-between items-center"
    >
      <!-- Branding -->
      <div class="mb-8 md:mb-0 text-center md:text-left">
        <img
          src="/ck.png"
          alt="Logo"
          class="w-32 h-32 mx-auto md:mx-0 mb-4 drop-shadow-[0_0_20px_rgba(34,211,238,0.5)]"
        />

        <p class="text-sm text-gray-400">
          &copy; {{ currentDate }} All rights reserved
        </p>
      </div>

      <!-- Quick Links -->
      <div class="mb-8 md:mb-0 text-center md:text-left">
        <h3 class="font-semibold mb-4 text-cyan-400">
          Quick Links
        </h3>

        <ul class="space-y-3 text-gray-300">
          <li>
            <a href="/#about" class="hover:text-cyan-400 transition">
              About Me
            </a>
          </li>

          <li>
            <a href="/#projects" class="hover:text-cyan-400 transition">
              Projects
            </a>
          </li>

          <li>
            <a href="/#contact" class="hover:text-cyan-400 transition">
              Contact
            </a>
          </li>

          <li>
            <a href="/cv.pdf" download class="hover:text-cyan-400 transition">
              Download CV
            </a>
          </li>

          <li>
            <a
              href="/certificates.pdf"
              download
              class="hover:text-cyan-400 transition"
            >
              Certificates
            </a>
          </li>
        </ul>
      </div>

      <!-- Social Links -->
      <div class="text-center md:text-right">
        <h3 class="font-semibold mb-4 text-cyan-400">
          Connect with me
        </h3>

        <div class="flex flex-col md:items-end space-y-3 text-gray-300">
          <a
            href="https://www.linkedin.com/in/chile-kasoka-402708195/"
            target="_blank"
            class="hover:text-cyan-400 transition"
          >
            LinkedIn
          </a>

          <a
            href="https://github.com/ChileKasoka"
            target="_blank"
            class="hover:text-cyan-400 transition"
          >
            GitHub
          </a>

          <a
            href="https://x.com/crzykyzy"
            target="_blank"
            class="hover:text-cyan-400 transition"
          >
            X
          </a>

          <a
            href="mailto:kasoka.chile@gmail.com"
            target="_blank"
            rel="noopener noreferrer"
            class="hover:text-cyan-400 transition"
          >
            Email
          </a>
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