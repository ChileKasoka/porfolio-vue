<template>
  <div class="bg-[#0b0f19] text-white overflow-hidden">

    <!-- HERO -->
    <section class="min-h-screen flex flex-col lg:flex-row items-center justify-center px-6 lg:px-20 py-20 relative">

      <!-- Glow background -->
      <div class="absolute inset-0 bg-gradient-to-br from-purple-900/30 via-transparent to-cyan-900/30 blur-3xl"></div>

      <!-- Image -->
      <div class="relative z-10">
        <img 
          src="/stunna.png"
          class="w-56 h-56 lg:w-80 lg:h-80 rounded-full object-cover border-4 border-cyan-500/40 shadow-[0_0_60px_rgba(34,211,238,0.4)] hover:scale-105 transition duration-500"
        />
      </div>

      <!-- Text -->
      <div class="z-10 max-w-2xl text-center lg:text-left mt-10 lg:mt-0 lg:ml-16">
        <h1 class="text-5xl lg:text-7xl font-extrabold leading-tight">
          Hi, I’m 
          <span class="bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
            Chile
          </span>
        </h1>

        <p class="mt-6 text-xl text-gray-300">
          I build scalable systems, powerful APIs, and modern web applications.
        </p>

        <div class="mt-8 flex flex-wrap gap-4 justify-center lg:justify-start">
          <a href="#contact" class="btn-primary">Hire Me</a>
          <a href="/Chilekesha_Kasoka_CV_2026.pdf" download class="btn-outline">
            Download CV
          </a>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section class="py-20 px-6 lg:px-20 bg-[#0f172a]">
      <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-12 items-center">

        <div>
          <h2 class="section-title text-sm">About Me</h2>
          <h3 class="text-3xl lg:text-5xl font-bold mt-4 text-cyan-400 font-coder">
            Design. Code. Deliver.
          </h3>

          <p class="mt-6 text-gray-300 leading-relaxed">
            I specialize in backend systems with Golang and scalable architectures.
            I design APIs, build real-world systems, and create solutions that are fast, secure, and production-ready.
          </p>
        </div>

        <!-- Stats -->
        <div class="grid grid-cols-2 gap-6">
          <div class="stat-card">
            <p id="projects-complete" class="stat-number">0</p>
            <span>Projects</span>
          </div>
          <div class="stat-card">
            <p id="experience" class="stat-number">0</p>
            <span>Years</span>
          </div>
          <div class="stat-card col-span-2">
            <p id="clients" class="stat-number">0</p>
            <span>Clients</span>
          </div>
        </div>

      </div>
    </section>

    <!-- EXPERIENCE -->
<section id="experience" class="py-20 px-6 bg-[#0b0f19]">
  <h2 class="section-title text-center">Experience</h2>

  <div class="relative max-w-5xl mx-auto mt-16">

    <!-- vertical line -->
    <div class="absolute left-4 md:left-1/2 transform md:-translate-x-1/2 w-[2px] h-full bg-gradient-to-b from-cyan-400 to-purple-500"></div>

    <div class="space-y-12">

      <div
        v-for="(job, index) in experiences"
        :key="index"
        class="relative flex flex-col md:flex-row items-start md:items-center"
      >

        <!-- dot -->
        <div class="absolute left-2 md:left-1/2 transform md:-translate-x-1/2 w-4 h-4 bg-cyan-400 rounded-full shadow-[0_0_10px_rgba(34,211,238,0.8)]"></div>

        <!-- card -->
        <div
          class="ml-10 md:ml-0 md:w-1/2"
          :class="index % 2 === 0 ? 'md:pr-10 md:text-right' : 'md:pl-10 md:ml-auto'"
        >
          <div class="glass-card hover:scale-[1.02] transition duration-300">

            <h3 class="text-xl font-bold text-cyan-400">
              {{ job.role }}
            </h3>

            <p class="text-sm text-gray-400 mt-1">
              {{ job.company }} • {{ job.period }}
            </p>

            <p class="text-gray-300 mt-4 text-sm leading-relaxed">
              {{ job.description }}
            </p>

            <!-- tech stack -->
            <div class="flex flex-wrap gap-2 mt-4"
                 :class="index % 2 === 0 ? 'md:justify-end' : ''">
              <span
                v-for="tech in job.tech"
                :key="tech"
                class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full"
              >
                {{ tech }}
              </span>
            </div>

          </div>
        </div>

      </div>

    </div>
  </div>
</section>

    <!-- PROJECTS -->
    <section class="py-20 px-6">
      <h2 class="section-title text-center">Projects</h2>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-10 max-w-7xl mx-auto mt-12">

        <div v-for="(project, index) in state.projects"
             :key="index"
             class="project-card group">

          <img :src="project.image" class="project-img" />

          <div class="p-6">
            <h3 class="text-xl font-bold group-hover:text-cyan-400 transition">
              {{ project.title }}
            </h3>

            <p class="text-gray-400 mt-2 text-sm">
              {{ project.description }}
            </p>

            <a :href="project.link" target="_blank" class="project-link">
              View →
            </a>
          </div>

        </div>

      </div>
    </section>

    <!-- SKILLS -->
    <section class="py-20 px-6 bg-[#0f172a]">
      <h2 class="section-title text-center">Tech Stack</h2>

      <div class="flex flex-wrap justify-center gap-4 mt-10">
        <div v-for="skill in skills"
             :key="skill.name"
             class="skill-pill">

          <img :src="skill.icon" class="w-5 mr-2"/>
          {{ skill.name }}

        </div>
      </div>
    </section>

    <!-- SERVICES -->
    <section class="py-20 px-6">
      <h2 class="section-title text-center">Services</h2>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto mt-12">

        <div v-for="service in services"
             :key="service.title"
             class="glass-card">

          <h3 class="text-xl font-bold text-cyan-400">
            {{ service.title }}
          </h3>

          <p class="text-gray-400 mt-3">
            {{ service.description }}
          </p>

        </div>

      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="py-20 px-6 bg-[#0f172a]">
      <h2 class="section-title text-center">Contact Me</h2>

      <form @submit.prevent="handleSubmit"
            class="max-w-2xl mx-auto mt-10 glass-card space-y-6">

        <input v-model="form.name" placeholder="Name" class="input"/>
        <input v-model="form.email" placeholder="Email" class="input"/>
        <textarea v-model="form.message" rows="5" placeholder="Message" class="input"/>

        <button class="btn-primary w-full">
          {{ loading ? "Sending..." : "Send Message" }}
        </button>

        <p v-if="success" class="text-green-400 text-center">Message sent!</p>
        <p v-if="error" class="text-red-400 text-center">Error sending message</p>

      </form>
    </section>

  </div>
</template>

<script setup>
import { reactive, ref, onMounted } from "vue";

const form = ref({ name: "", email: "", message: "" });
const loading = ref(false);
const success = ref(false);
const error = ref(false);

const FORMSPREE_URL = "https://formspree.io/f/xnnbwypj";

const handleSubmit = async () => {
  loading.value = true;
  try {
    const res = await fetch(FORMSPREE_URL, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(form.value),
    });

    success.value = res.ok;
    error.value = !res.ok;
  } catch {
    error.value = true;
  }
  loading.value = false;
};

const experiences = [
  {
    role: "Software Developer",
    company: "Freelance / Personal Projects",
    period: "2023 - Present",
    description:
      "Building scalable full-stack applications using Golang, Vue.js, and PostgreSQL. Designed RBAC systems, project management tools, and real-world production-ready APIs.",
    tech: ["Golang", "Vue.js", "PostgreSQL", "Docker"],
  },
  {
    role: "Systems Developer",
    company: "USAID Supply Chain System (eLMIS)",
    period: "2024",
    description:
      "Worked on supply chain systems handling inventory, orders, and supplier tracking with real-time updates and data reliability.",
    tech: ["DHIS2", "APIs", "Data Systems"],
  },
  {
    role: "IT Support / Networking",
    company: "Various Organizations",
    period: "2022 - 2023",
    description:
      "Handled network setup, troubleshooting, and infrastructure support ensuring reliable connectivity and system uptime.",
    tech: ["Networking", "Linux", "Troubleshooting"],
  },
];

const state = reactive({
  projects: [
    {
      title: "Construction Management App",
      description: "RBAC, project tracking, role system",
      image: "/construction.png",
      link: "https://github.com/ChileKasoka/csm",
    },
    {
      title: "USAID Supply Chain System",
      description: "Inventory + supplier tracking",
      image: "/DHIS2.png",
      link: "https://zm-elmis.org/",
    },
    {
      title: "Church Management System",
      description: "ERP for church operations",
      image: "/shield.png",
      link: "https://sci-eld.org/",
    },
  ],
});

const skills = [
  { name: "Vue.js", icon: "/icons/vue.svg" },
  { name: "Golang", icon: "/icons/golang.svg" },
  { name: "PostgreSQL", icon: "/icons/psql.svg" },
  { name: "Docker", icon: "/icons/docker.svg" },
];

const services = [
  { title: "Web Development", description: "Modern apps" },
  { title: "Backend APIs", description: "Secure + scalable" },
  { title: "Cloud", description: "Deployments + infra" },
];

const animateCounter = (id, target) => {
  let count = 0;
  const interval = setInterval(() => {
    count++;
    document.getElementById(id).innerText = count;
    if (count >= target) clearInterval(interval);
  }, 40);
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

/* Buttons */
.btn-primary {
  @apply px-6 py-3 rounded-full bg-gradient-to-r from-cyan-500 to-purple-500 font-semibold shadow-lg hover:scale-105 transition;
}

.btn-outline {
  @apply px-6 py-3 rounded-full border border-gray-500 hover:border-cyan-400 transition;
}

/* Cards */
.glass-card {
  @apply bg-white/5 backdrop-blur-lg border border-white/10 p-6 rounded-2xl shadow-xl;
}

.project-card {
  @apply bg-[#111827] rounded-2xl overflow-hidden border border-white/10 hover:shadow-[0_0_30px_rgba(34,211,238,0.2)] transition;
}

.project-img {
  @apply w-full h-48 object-cover;
}

.project-link {
  @apply inline-block mt-4 text-cyan-400 hover:underline;
}

/* Skills */
.skill-pill {
  @apply flex items-center px-5 py-2 rounded-full bg-white/5 border border-white/10 text-sm hover:bg-cyan-500/20 transition;
}

/* Stats */
.stat-card {
  @apply bg-white/5 border border-white/10 p-6 rounded-xl text-center;
}

.stat-number {
  @apply text-3xl font-bold text-cyan-400;
}

/* Inputs */
.input {
  @apply w-full px-4 py-3 rounded-lg bg-white/5 border border-white/10 focus:outline-none focus:ring-2 focus:ring-cyan-400;
}

/* Titles */
.section-title {
  @apply text-3xl lg:text-5xl font-extrabold text-cyan-400;
}
</style>