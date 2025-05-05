<template>
    <div class=" bottom-0">
        <p class=" text-gray-800 text-center">&copy; {{ currentDate }} stunna. All rights reserved</p>
    </div>
</template>

<script setup>
   const currentDate = new Date().getFullYear();
</script>