<template>
    <div class=" bg-gradient-to-r from-slate-800 via-blue-900 to-slate-900 text-white flex flex-col justify-center items-center py-20 px-6 lg:px-20">
      <!-- Hero Section -->
      <div class="min-h-screen items-center justify-center space-y-8 animate-fade-in">
        <div class="container flex-col-reverse lg:flex-row pt-20 flex items-center">
        <!-- Profile Image -->
        <div class="mx-auto mb-8">
          <img 
            src="/stunna.png" 
            alt="My Profile Image" 
            class="w-48 h-48 lg:w-64 lg:h-64 object-cover rounded-full shadow-xl transform hover:scale-105 transition-all duration-300"
          />
        </div>
          <div class="about text-right ml-auto mr-0">
            <p class="font-tagesschrift text-amber-700 text-3xl lg:text-5xl font-extrabold xl:text-6xl tracking-wide">
            Hello World
            </p>
            <br>
            <h1 class="text-4xl lg:text-5xl xl:text-8xl font-extrabold leading-tight">
              I'm Chile, a Software Developer
            </h1>
            <br>
            <p class="text-amber-700 text-xl font-light">
              in a muiltiverse of other things...
            </p>
            <br>
            <button class=" bg-gray-900 hover:bg-amber-700 text-amber-700 hover:text-white font-semibold py-3 px-6 rounded-full shadow-md transition duration-300">
              Get in Touch
            </button>
          </div>
        </div>
      </div>

      <div class="min-h-screen w-full flex flex-col md:flex-row px-4 md:px-12 py-8 gap-8">
  <!-- About Section -->
  <div class="w-full md:w-3/4">
    <section data-aos="fade-up" class="text-left mt-8 space-y-4">
      <h2 class="text-2xl font-light text-amber-700">About Me</h2>
      <h3 class="text-4xl font-extrabold text-amber-700">Design, Code, Repeat</h3>
      <p class="text-xl text-gray-200">
        I'm a result-oriented Software Developer who crafts fast, scalable, and elegant web solutions—
        <br>turning complex problems into clean, user-friendly experiences.
        <br>
        I specialize in creating scalable, efficient, and user-friendly applications with over 3 years of experience in both frontend and backend technologies.
      </p>
    </section>
  </div>

  <!-- Stats Section -->
  <div class="w-full md:w-1/2">
    <section class="grid grid-cols-1 sm:grid-cols-2 gap-8 mt-8">
      <!-- Projects Completed -->
      <div>
        <div class="flex items-center text-5xl font-extrabold text-blue-700">
          <p id="projects">0</p>
          <span class="text-plus">+</span>
        </div>
        <h3 class="text-xl font-semibold mt-2">Projects Completed</h3>
      </div>

      <!-- Years of Experience -->
      <div>
        <div class="flex items-center text-5xl font-extrabold text-green-600">
          <p id="experience">0</p>
          <span class="text-plus">+</span>
        </div>
        <h3 class="text-xl font-semibold mt-2">Years of Experience</h3>
      </div>

      <!-- Happy Clients -->
      <div>
        <div class="flex items-center text-5xl font-extrabold text-purple-600">
          <p id="clients">0</p>
          <span class="text-plus">+</span>
        </div>
        <h3 class="text-xl font-semibold mt-2">Happy Clients</h3>
      </div>
    </section>
  </div>
</div>


      <div class="project-section">
        <section class="py-20 px-4">
          <h2 class="text-4xl lg:text-5xl font-extrabold text-center mb-12 text-amber-700">
            Featured Projects
          </h2>

          <div class="grid gap-10 sm:grid-cols-2 lg:grid-cols-3 max-w-7xl mx-auto">
            <div
              v-for="(project, index) in state.projects"
              :key="index"
              class="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-2xl transition-shadow duration-300"
            >
              <img :src="project.image" :alt="project.title" class="w-full h-48 object-cover" />
              <div class="p-6 space-y-3">
                <h3 class="text-2xl font-semibold text-[#054861]">{{ project.title }}</h3>
                <p class="text-gray-700 text-base">{{ project.description }}</p>
                <a
                  :href="project.link"
                  target="_blank"
                  class="inline-block mt-4 text-[#054861] font-medium hover:underline"
                >
                  View Project →
                </a>
              </div>
            </div>
          </div>
        </section>
      </div>

      <div class="services text-center mt-20 mb-20">
        <h2 class="text-2xl text-amber-700">Services</h2>
        <p class="text-4xl text-amber-700 font-extrabold">Tailored Solutions Offered</p>
      </div>

      <div class=" w-full">
        <div class="flex flex-col min-h-screen md:flex-row items-start gap-8 w-full">
          <!-- Left Column -->
          <div class="w-full md:w-1/2 text-left space-y-4">
            <h1 class="text-3xl text-amber-700 font-extrabold">
              UX/UI Design & Frontend Technologies
            </h1>
            <p class="text-white text-2xl">
              I craft engaging user interfaces and smooth user experiences for both web and mobile apps, using modern frameworks and a keen eye for design best practices.
            </p>
          </div>

          <!-- Right Column: Tech Icons -->
          <div class="w-full md:w-1/2 flex flex-wrap gap-4 items-start pt-4">
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/figma.svg" alt="Figma" class="w-5 h-5 mr-2" /> Figma
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/react.svg" alt="React" class="w-5 h-5 mr-2" /> React
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/tailwind.svg" alt="Tailwind" class="w-5 h-5 mr-2" /> Tailwind
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/vue.svg" alt="VueJs" class="w-5 h-5 mr-2" /> VueJs
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/flutter.svg" alt="Flutter" class="w-5 h-5 mr-2" /> Flutter
            </span>
          </div>
        </div>

        <div class="min-h-screen flex flex-col md:flex-row items-start justify-between px-6 gap-8">


          <!-- Right Column: Tech Icons -->
          <div class="w-full md:w-1/2 flex flex-wrap justify-end gap-4 pt-4">
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/node.svg" alt="NodeJS" class="w-5 h-5 mr-2" /> NodeJS
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/golang.svg" alt="Golang" class="w-5 h-5 mr-2" /> Golang
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/php.svg" alt="PHP" class="w-5 h-5 mr-2" /> PHP
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/spring.svg" alt="Spring" class="w-5 h-5 mr-2" /> Spring Framework
            </span>
          </div>
          <!-- Left Column: Text -->
          <div class="w-full md:w-1/2 text-right space-y-4">
            <h1 class="text-3xl text-amber-700 font-extrabold">
              Server Side Solutions
            </h1>
            <p class="text-white text-2xl">
              I build robust and scalable backend systems using Golang, Node.js, and PostgreSQL, with a strong focus on performance, security, and seamless integration with frontend frameworks.
            </p>
          </div>
        </div>


        <div class="min-h-screen flex flex-col md:flex-row items-start justify-between px-6 gap-8">
          <!-- Left Column: Text -->
          <div class="w-full md:w-1/2 text-left space-y-4 pr-0 md:pr-8">
            <h1 class="text-3xl text-amber-700 font-extrabold">Cloud and DevOps</h1>
            <p class="text-white text-2xl">
              Containerized backend services for consistent development and deployment across environments.<br>
              I utilize Docker and Kubernetes for efficient orchestration and scaling of applications.<br>
              Deploy scalable APIs and services using EC2, S3, and RDS. Configure environments with IAM and monitor with CloudWatch.
            </p>
          </div>

          <!-- Right Column: Tech Icons -->
          <div class="w-full md:w-1/2 flex flex-wrap justify-start gap-4 pt-4">
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/docker.svg" alt="Docker" class="w-5 h-5 mr-2" /> Docker
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/kubernetes.svg" alt="Kubernetes" class="w-5 h-5 mr-2" /> Kubernetes
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/aws.svg" alt="AWS" class="w-5 h-5 mr-2" /> AWS
            </span>
            <span class="flex items-center bg-gray-900 px-6 py-3 rounded-full text-white text-lg">
              <img src="/icons/github.svg" alt="GitHub" class="w-5 h-5 mr-2" /> GitHub
            </span>
          </div>
        </div>
      </div>

      <section class="min-h-screen w-full md:w-1/2 px-4 py-16 flex items-center justify-center">
        <div class="w-full bg-gray-800 p-8 rounded-lg shadow-lg">
          <h2 class="text-3xl font-bold text-white mb-6 text-center">Have a project in mind ?</h2>
          <p class="text-2xl font-light text-center">Get in Touch</p>
          <br>
          <form action="#" method="POST" class="space-y-6">
            
            <!-- Name -->
            <div>
              <label for="name" class="block text-white text-sm font-semibold mb-2">Your Name</label>
              <input type="text" id="name" name="name" required
                class="w-full px-4 py-3 rounded-lg bg-gray-700 text-white focus:outline-none focus:ring-2 focus:ring-amber-500" />
            </div>

            <!-- Email -->
            <div>
              <label for="email" class="block text-white text-sm font-semibold mb-2">Email Address</label>
              <input type="email" id="email" name="email" required
                class="w-full px-4 py-3 rounded-lg bg-gray-700 text-white focus:outline-none focus:ring-2 focus:ring-amber-500" />
            </div>

            <!-- Message -->
            <div>
              <label for="message" class="block text-white text-sm font-semibold mb-2">Your Message</label>
              <textarea id="message" name="message" rows="5" required
                class="w-full px-4 py-3 rounded-lg bg-gray-700 text-white focus:outline-none focus:ring-2 focus:ring-amber-500"></textarea>
            </div>

            <!-- Submit -->
            <div class="text-center">
              <button type="submit"
                class="bg-amber-600 hover:bg-amber-700 text-white font-semibold px-6 py-3 rounded-full transition duration-300">
                Send Message
              </button>
            </div>
          </form>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  function handleDownload() {
    // You can link to your CV file here
    window.open('/your-cv.pdf', '_blank');
  }
  
import { reactive } from 'vue';

const state = reactive({
  projects: [
    {
      title: "Construction Manager",
      description: "A project management tool for construction teams",
      image: "/construction.png",
      link: "https://example.com/construction",
    },
    {
      title: "Appointment Scheduler",
      description: "Book appointments with ease",
      image: "/book.png",
      link: "https://example.com/real-estate",
    },
    {
      title: "ELMIS",
      description: "Electronic Logistics Management Information System under USAID",
      image: "/elmis.png",
      link: "https://openlmis.org/implementation_region/zambia/",
    },
  ],
});

  function animateCounter(id, target, duration = 4000) {
    const el = document.getElementById(id);
    let start = 0;
    const increment = target / (duration / 16); // 60 FPS approx.

    const updateCounter = () => {
      start += increment;
      if (start < target) {
        el.textContent = Math.floor(start);
        requestAnimationFrame(updateCounter);
      } else {
        el.textContent = target;
      }
    };

    updateCounter();
  }

  window.addEventListener('DOMContentLoaded', () => {
    animateCounter('projects', 4);
    animateCounter('experience', 3);
    animateCounter('clients', 3);
  });
  </script>
  
  <style scoped>
  @keyframes fadeIn {
    0% {
      opacity: 0;
      transform: translateY(40px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .animate-fade-in {
    animation: fadeIn 1.2s ease-out;
  }
  </style>
  