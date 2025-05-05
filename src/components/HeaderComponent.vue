<template>
    <div class="h-24 flex justify-between px-8 lg:px-20 py-6 bg-gradient-to-r from-blue-800 via-blue-900 to-slate-900 shadow-lg items-center">
      <!-- Logo -->
      <div>
        <img src="/myworld.png" height="150" width="150" alt="myworld Image" class="mr-2 transform hover:scale-105 transition-all duration-300" />
      </div>
      
      <!-- Links -->
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
    </div>
  </template>
  
  <script>
    export default {
      data() {
        return {
          links: [
            { text: 'About', route: 'about' },
            { text: 'Experience', route: 'experience' },
            { text: 'Featured Projects', route: 'featured-projects' },
            { text: "Let's Connect", route: 'lets-connect' },
          ],
        };
      },
    };
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
  