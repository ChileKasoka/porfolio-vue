<template>
    <div class="flex justify-between px-20 h-18 bg-[#bbbbbb] items-center">
        <div class="">
            <img src="/myworld.png" height="200" width="200" alt="myworld Image" class="mr-2" />
        </div>
        <ul class="hidden lg:flex justify-end space-x-5">
            <li v-for="(link, index) in links" :key="index">
                <router-link :to="link.route" class="text-gray-700 hover:text-gray-900 hover:underline text-xl">
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