<template>
  <div class="flex items-center gap-5 mt-6">

    <!-- GitHub -->
    <a href="https://github.com/ChileKasoka" target="_blank" class="social-icon">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24" class="w-6 h-6">
        <path d="M12 .5C5.73.5.98 5.25.98 11.53c0 4.86 3.15 8.98 7.52 10.43.55.1.75-.24.75-.53v-1.87c-3.06.66-3.7-1.47-3.7-1.47-.5-1.26-1.23-1.6-1.23-1.6-1-.68.08-.67.08-.67 1.1.08 1.67 1.12 1.67 1.12.97 1.67 2.55 1.18 3.17.9.1-.7.38-1.18.68-1.45-2.44-.28-5-1.22-5-5.43 0-1.2.43-2.17 1.12-2.94-.11-.27-.49-1.38.11-2.88 0 0 .92-.3 3.02 1.12.88-.24 1.83-.36 2.77-.36.94 0 1.9.12 2.77.36 2.1-1.42 3.02-1.12 3.02-1.12.6 1.5.22 2.61.11 2.88.7.77 1.12 1.74 1.12 2.94 0 4.22-2.56 5.14-5 5.42.39.34.73 1 .73 2.02v3c0 .3.2.64.76.53 4.36-1.45 7.51-5.57 7.51-10.43C23.02 5.25 18.27.5 12 .5z"/>
      </svg>
    </a>

    <!-- LinkedIn -->
    <a href="https://www.linkedin.com/in/chile-kasoka-402708195/" target="_blank" class="social-icon">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24" class="w-6 h-6">
        <path d="M4.98 3.5C4.98 5 3.88 6.1 2.4 6.1 1 6.1 0 5 0 3.5 0 2 1.1.9 2.5.9c1.38 0 2.48 1.1 2.48 2.6zM.5 8h4v12h-4V8zm7 0h3.8v1.7h.05c.53-1 1.83-2 3.77-2 4 0 4.73 2.6 4.73 6v6.3h-4v-5.6c0-1.3-.02-3-1.83-3-1.84 0-2.12 1.44-2.12 2.9v5.7h-4V8z"/>
      </svg>
    </a>

    <!-- Twitter / X -->
    <a href="https://x.com/crzykyzy" target="_blank" class="social-icon">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24" class="w-6 h-6">
        <path d="M22.46 6c-.77.35-1.6.58-2.46.69a4.28 4.28 0 001.88-2.36 8.53 8.53 0 01-2.7 1.03 4.26 4.26 0 00-7.26 3.88A12.1 12.1 0 013 4.79a4.25 4.25 0 001.32 5.67c-.66-.02-1.28-.2-1.82-.5v.05a4.27 4.27 0 003.42 4.18c-.32.09-.66.14-1 .14-.25 0-.5-.02-.73-.07a4.27 4.27 0 003.98 2.97A8.55 8.55 0 012 19.54a12.06 12.06 0 006.53 1.91c7.84 0 12.12-6.5 12.12-12.12 0-.18-.01-.35-.02-.53A8.66 8.66 0 0024 5.1a8.4 8.4 0 01-2.54.7z"/>
      </svg>
    </a>

  </div>
</template>

<script setup>
// no logic needed (pure UI component)
</script>

<style scoped>
.social-icon {
  @apply text-gray-400 transition-all duration-300;
}

.social-icon:hover {
  color: #22d3ee;
  transform: translateY(-3px) scale(1.1);
  filter: drop-shadow(0 0 8px rgba(34, 211, 238, 0.6));
}
</style>