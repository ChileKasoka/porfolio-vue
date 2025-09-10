<template>
  <div class="bg-white text-gray-900 flex flex-col justify-center items-center">
    <!-- Hero -->
    <section id="home" class="min-h-screen flex flex-col-reverse lg:flex-row items-center justify-center gap-12 px-6 lg:px-20 py-24 animate-fade-in">
      <div class="mx-auto lg:mx-0">
        <img 
          src="/stunna.png" 
          alt="Profile Image" 
          class="w-52 h-52 lg:w-72 lg:h-72 object-cover rounded-full shadow-2xl transform hover:scale-105 transition-all duration-500"
        />
      </div>
      <div class="text-center lg:text-left max-w-2xl">
        <h1 class="text-5xl lg:text-6xl xl:text-7xl font-extrabold leading-tight text-slate-900">
          Hi, I’m <span class="text-amber-600">Chile</span>
        </h1>
        <p class="mt-6 text-2xl lg:text-3xl font-light text-gray-700">
          Software Developer specializing in scalable, efficient, and user-friendly applications.
        </p>
        <p class="mt-4 text-lg text-gray-600">
          I turn complex challenges into elegant digital solutions—balancing performance, clean design, and usability.
        </p>
        <div class="mt-8 flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
          <button class="bg-amber-600 hover:bg-amber-700 text-white font-semibold py-3 px-8 rounded-full shadow-lg transition duration-300">
            Get in Touch
          </button>
          <a 
            href="/Chilekesha-Kasoka-Resume.pdf" 
            download 
            class="bg-slate-900 hover:bg-slate-800 text-white font-semibold py-3 px-8 rounded-full shadow-lg transition duration-300"
          >
            Download CV
          </a>
        </div>
      </div>
    </section>

    <!-- About + Stats -->
    <section id="about" class="w-full flex flex-col md:flex-row px-6 lg:px-20 py-20 gap-12 font-coder bg-gray-900 text-gray-100">
      <div class="w-full md:w-3/4 space-y-6">
        <h2 class="text-2xl font-semibold text-amber-400">About Me</h2>
        <h3 class="text-3xl lg:text-5xl font-extrabold text-cyan-400">Design. Code. Deliver.</h3>
        <p class="text-xl text-gray-300 leading-relaxed">
          I’m a results-oriented developer passionate about turning complex requirements into clean, 
          performant, and user-centric applications. My focus is on building scalable web solutions 
          that blend modern design practices with solid backend architecture.
        </p>
      </div>
      <div class="w-full md:w-1/2 grid grid-cols-1 sm:grid-cols-2 gap-10">
        <div class="text-center">
          <div class="text-5xl font-extrabold text-blue-400">
            <p id="projects-complete">0</p><span>+</span>
          </div>
          <h3 class="text-lg font-medium mt-2 text-gray-200">Projects Completed</h3>
        </div>
        <div class="text-center">
          <div class="text-5xl font-extrabold text-green-400">
            <p id="experience">0</p><span>+</span>
          </div>
          <h3 class="text-lg font-medium mt-2 text-gray-200">Years of Experience</h3>
        </div>
        <div class="text-center">
          <div class="text-5xl font-extrabold text-purple-400">
            <p id="clients">0</p><span>+</span>
          </div>
          <h3 class="text-lg font-medium mt-2 text-gray-200">Happy Clients</h3>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects" class="project-section bg-slate-50 w-full py-20 px-6">
      <h2 class="text-4xl lg:text-5xl font-extrabold text-center mb-12 text-amber-600">Featured Projects</h2>
      <div class="grid gap-10 sm:grid-cols-2 lg:grid-cols-3 max-w-7xl mx-auto">
        <div
          v-for="(project, index) in state.projects"
          :key="index"
          class="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-2xl transition-shadow duration-300"
        >
          <img :src="project.image" :alt="project.title" class="w-full h-52 object-cover" />
          <div class="p-6 space-y-3">
            <h3 class="text-2xl font-semibold text-slate-900">{{ project.title }}</h3>
            <p class="text-gray-600 text-base">{{ project.description }}</p>
            <a
              :href="project.link"
              target="_blank"
              class="inline-block mt-4 text-amber-600 font-medium hover:underline"
            >
              View Project →
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section class="py-20 px-6 bg-white w-full">
      <h2 class="text-4xl lg:text-5xl font-extrabold text-center mb-12 text-amber-600">Skills</h2>
      <div class="flex flex-wrap justify-center gap-6 max-w-4xl mx-auto">
        <div
          v-for="(skill, index) in skills"
          :key="index"
          class="flex items-center bg-slate-800 px-6 py-3 rounded-full text-white text-lg shadow-sm"
        >
          <img :src="skill.icon" :alt="skill.name" class="w-5 h-5 mr-2" />
          {{ skill.name }}
        </div>
      </div>
    </section>

    <!-- Services -->
    <section id="services" class="py-20 px-6 bg-slate-50 w-full">
      <h2 class="text-4xl lg:text-5xl font-extrabold text-center mb-12 text-amber-600">Services</h2>
      <div class="grid gap-10 sm:grid-cols-2 lg:grid-cols-3 max-w-7xl mx-auto">
        <div v-for="(service, index) in services" :key="index" class="bg-white p-8 rounded-2xl shadow-md hover:shadow-xl transition">
          <h3 class="text-2xl font-bold text-slate-900 mb-3">{{ service.title }}</h3>
          <p class="text-gray-600 text-base">{{ service.description }}</p>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="py-20 px-6 bg-white text-center w-full">
      <h2 class="text-4xl lg:text-5xl font-extrabold mb-6 text-amber-600">Let’s Work Together</h2>
      <p class="text-lg text-gray-700 mb-8">
        Interested in collaborating or hiring me? I’m just an email away.
      </p>
      <a href="mailto:your.email@example.com" class="bg-amber-600 hover:bg-amber-700 text-white font-semibold py-3 px-8 rounded-full shadow-lg transition duration-300">
        Contact Me
      </a>
    </section>
  </div>
</template>

<script setup>
import { reactive, onMounted } from "vue";

const state = reactive({
  projects: [
    {
      title: "Construction Management App",
      description: "Full-stack system with RBAC, project tracking, and role management.",
      image: "/construction.png",
      link: "https://github.com/yourrepo/construction",
    },
    {
      title: "Electronic Supply Chain Management Information System USAID",
      description: "tracks orders, inventory, and suppliers with real-time updates.",
      image: "/elmis.png",
      link: "https://github.com/yourrepo/realestate",
    },
    {
      title: "Appointment Booking System",
      description: "Appointment scheduling with email notifications and calendar integration.",
      image: "/book.png",
      link: "https://github.com/yourrepo/budget",
    },
  ],
});

const skills = [
  { name: "Vue.js", icon: "/icons/vue.svg" },
  { name: "React", icon: "/icons/reactjs.svg" },
  { name: "Golang", icon: "/icons/golang.svg" },
  { name: "Spring Boot", icon: "/icons/spring.svg" },
  { name: "Node.js", icon: "/icons/node.svg" },
  { name: "PostgreSQL", icon: "/icons/psql.svg" },
  { name: "Flutter", icon: "/icons/flutter.svg" },
  { name: "Docker", icon: "/icons/docker.svg" },
  { name: "Linux", icon: "/icons/linux.svg" },
  { name: "AWS", icon: "/icons/aws.svg" },
];

const services = [
  { title: "Web Development", description: "Building scalable, responsive, and modern web apps tailored to client needs." },
  { title: "Backend APIs", description: "Designing and implementing secure, high-performance REST APIs." },
  { title: "Database Design", description: "Efficient schema design and optimization for PostgreSQL & SQL-based systems." },
];

const animateCounter = (id, target) => {
  let count = 0;
  const interval = setInterval(() => {
    count++;
    document.getElementById(id).innerText = count;
    if (count >= target) clearInterval(interval);
  }, 50);
};

onMounted(() => {
  animateCounter("projects-complete", 12);
  animateCounter("experience", 4);
  animateCounter("clients", 5);
});
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

.font-coder {
  font-family: 'Press Start 2P', cursive;
}
</style>