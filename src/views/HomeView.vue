<template>
  <div class="flex bg-[#0b0f19] text-white">

    <!-- SIDEBAR -->
    <aside class="hidden lg:flex flex-col justify-between w-72 h-screen fixed left-0 top-0 bg-[#0f172a] border-r border-white/10 p-6">

      <!-- Top -->
      <div>
        <div class="flex flex-col items-left text-left">

          <img
            src="/stunna.jpg"
            class="w-32 h-32 rounded-full border-4 border-cyan-500/40 shadow-[0_0_40px_rgba(34,211,238,0.4)]"
          />

          <h2 class="mt-4 text-xl font-bold">Chilekesha Kasoka</h2>
          <p class="text-gray-400 text-sm">COMPUTER SYSTEMS ENGINEER</p>

        </div>

        <!-- NAV -->
        <nav class="mt-10 space-y-4">
          <a
            v-for="link in links"
            :key="link.href"
            @click.prevent="scrollToSection(link.href)"
            :href="link.href"
            :class="[
              'sidebar-link',
              activeSection === link.href ? 'sidebar-active' : ''
            ]"
          >
            {{ link.text }}
          </a>
        </nav>
      </div>

      <div class="text-xs text-gray-500 text-left">
        © {{ new Date().getFullYear() }}
      </div>

    </aside>

    <!-- MOBILE TOP BAR -->
    <div class="lg:hidden fixed top-0 w-full bg-[#0f172a] border-b border-white/10 p-4 flex justify-between z-50">
      <span class="font-bold">$ ck</span>
      <button @click="toggleMenu">☰</button>
    </div>

    <!-- MOBILE MENU -->
    <div v-if="isMenuOpen"
         class="lg:hidden fixed inset-0 bg-black/80 backdrop-blur-md flex flex-col items-center justify-center space-y-6 z-50">

      <a
        v-for="link in links"
        :key="link.href"
        @click="scrollToSection(link.href); toggleMenu()"
        class="text-xl"
      >
        {{ link.text }}
      </a>

    </div>

    <!-- MAIN -->
    <main class="w-full lg:ml-72 bg-white text-gray-900 dark:bg-[#0b0f19] dark:text-white transition-colors duration-300">

      <!-- THEME TOGGLE -->
      <div class="fixed top-16 right-6 z-50">
        <button
          @click="toggleTheme"
          class="px-4 py-2 rounded-full bg-gray-200 dark:bg-[#1e293b] text-sm font-semibold shadow hover:scale-105 transition"
        >
          {{ isDark ? "☀️ Light" : "🌙 Dark" }}
        </button>
      </div>

      <!-- HERO -->
      <section id="home" class="min-h-screen px-6 flex flex-col justify-center">

        <h1 class="text-5xl lg:text-7xl font-extrabold">
          Hi, I’m <span class="gradient-text">Chile</span>
        </h1>

    <p class="mt-6 text-gray-700 dark:text-gray-300 w-full leading-relaxed">
      I’m a Computer Systems Engineer with experience across software development, cloud, database management, networking, and IT systems. 
      I build scalable applications and APIs using Spring Boot (Java), Golang, and modern web technologies, 
      while also working with system infrastructure, troubleshooting, and network environments.  
      <br /><br />
      I focus on designing efficient, secure, and reliable solutions—whether it’s developing backend systems, 
      optimizing performance, or supporting real-world IT operations.
    </p>

        <SocialMedia />

        <div class="mt-8 flex gap-4">
          <a href="#contact" class="btn-primary">Hire Me</a>
          <a href="/Chilekesha_Kasoka_CV_2026.pdf" download class="btn-outline">CV</a>
        </div>

      </section>

      <!-- ABOUT -->
      <section id="about" class="min-h-screen px-6 flex flex-col justify-center">

        <h2 class="section-title">About</h2>

    <p class="text-gray-700 dark:text-gray-300 mt-6 max-w-3xl leading-relaxed">
      I’m a Computer Systems Engineer and backend-focused software developer with over 
      <span class="text-cyan-500 dark:text-cyan-400 font-semibold">4+ years of experience</span> 
      building scalable systems, high-performance APIs, and real-world applications. 
      I specialize in Spring Boot (Java), Golang, and modern web technologies, 
      with a strong focus on performance, clean architecture, and reliability.
      <br /><br />
      I’ve worked on systems ranging from supply chain platforms to full-stack applications, implementing 
      solutions such as role-based access control (RBAC), project management systems, and production-ready APIs.
      <br /><br />
      With a strong systems engineering foundation, I focus on building software that scales and lasts.
    </p>

        <!-- STATS -->
        <div class="grid grid-cols-2 md:grid-cols-3 gap-6 mt-12 max-w-2xl">

          <div class="stat-card">
            <p id="projects-complete" class="stat-number">0</p>
            <span class="text-gray-500 dark:text-gray-400 text-sm">Projects</span>
          </div>

          <div class="stat-card">
            <p id="experience-years" class="stat-number">0</p>
            <span class="text-gray-500 dark:text-gray-400 text-sm">Years</span>
          </div>

          <div class="stat-card">
            <p id="clients" class="stat-number">0</p>
            <span class="text-gray-500 dark:text-gray-400 text-sm">Clients</span>
          </div>

        </div>

      </section>

      <!-- EXPERIENCE -->
      <section id="experience" class="min-h-screen px-6">

        <h2 class="section-title">Experience</h2>

        <div class="mt-10 space-y-6">
          <div
            v-for="(job, index) in experiences"
            :key="job.role + index"
            class="glass-card"
          >
            <h3 class="text-cyan-500 dark:text-cyan-400 font-bold">
              {{ job.role }}
            </h3>

            <p class="text-sm text-gray-500 dark:text-gray-400">
              {{ job.company }} • {{ job.period }}
            </p>

            <p class="mt-3 text-gray-700 dark:text-gray-300 text-sm">
              {{ job.description }}
            </p>

          </div>
        </div>

      </section>

      <!-- PROJECTS -->
      <section id="projects" class="px-6 min-h-screen">

        <h2 class="section-title">Projects</h2>

        <div class="grid md:grid-cols-2 gap-8 mt-10">

          <div
            v-for="(project, index) in state.projects"
            :key="index"
            class="project-card"
          >
            <img :src="project.image" class="project-img" />

            <div class="p-4">
              <h3 class="font-bold">
                {{ project.title }}
              </h3>

              <p class="text-sm text-gray-600 dark:text-gray-400 mt-2">
                {{ project.description }}
              </p>
            </div>

          </div>

        </div>

      </section>

      <!-- CONTACT -->
      <section id="contact" class="min-h-screen flex flex-col justify-center items-center px-6">

        <h2 class="section-title">Contact</h2>

<form @submit.prevent="handleSubmit" class="max-w-xl mt-8 space-y-4 w-full">

  <!-- NAME -->
  <input
    v-model="form.name"
    placeholder="Name"
    class="input border border-gray-400 dark:border-white/10
           bg-white dark:bg-white/5
           text-gray-900 dark:text-white
           placeholder-gray-500 dark:placeholder-gray-500
           focus:border-cyan-500 dark:focus:border-cyan-400
           shadow-sm dark:shadow-none"
  />

  <!-- EMAIL -->
  <input
    v-model="form.email"
    placeholder="Email"
    class="input border border-gray-400 dark:border-white/10
           bg-white dark:bg-white/5
           text-gray-900 dark:text-white
           placeholder-gray-500 dark:placeholder-gray-500
           focus:border-cyan-500 dark:focus:border-cyan-400
           shadow-sm dark:shadow-none"
  />

  <!-- MESSAGE -->
  <textarea
    v-model="form.message"
    rows="4"
    placeholder="Message"
    class="input border border-gray-800 dark:border-white/10
           bg-white dark:bg-white/5
           text-gray-900 dark:text-white
           placeholder-gray-500 dark:placeholder-gray-500
           focus:border-cyan-500 dark:focus:border-cyan-400
           shadow-sm dark:shadow-none"
  />

  <button class="btn-primary w-full">
    {{ loading ? "Sending..." : "Send Message" }}
  </button>

</form>

      </section>

      <FooterView />

    </main>
  </div>
</template>

<script setup>
import { ref, reactive, onMounted, onUnmounted } from "vue";
import FooterView from "../components/FooterView.vue";
import SocialMedia from "../components/SocialMedia.vue";

/* =========================
   THEME
========================= */
const isDark = ref(true);

const toggleTheme = () => {
  isDark.value = !isDark.value;

  const html = document.documentElement;

  if (isDark.value) {
    html.classList.add("dark");
    localStorage.setItem("theme", "dark");
  } else {
    html.classList.remove("dark");
    localStorage.setItem("theme", "light");
  }
};

/* =========================
   INIT THEME + LIFE CYCLE
========================= */
onMounted(() => {
  const saved = localStorage.getItem("theme");

  if (saved === "light") {
    isDark.value = false;
    document.documentElement.classList.remove("dark");
  } else {
    isDark.value = true;
    document.documentElement.classList.add("dark");
  }

  window.addEventListener("scroll", handleScroll);

  animateCounter("projects-complete", 12);
  animateCounter("experience-years", 4);
  animateCounter("clients", 5);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});

/* =========================
   FORM
========================= */
const form = ref({ name: "", email: "", message: "" });
const loading = ref(false);

const FORMSPREE_URL = "https://formspree.io/f/xnnbwypj";

const handleSubmit = async () => {
  loading.value = true;

  try {
    await fetch(FORMSPREE_URL, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(form.value),
    });

    form.value = { name: "", email: "", message: "" };
  } finally {
    loading.value = false;
  }
};

/* =========================
   NAV
========================= */
const links = [
  { text: "Home", href: "#home" },
  { text: "About", href: "#about" },
  { text: "Experience", href: "#experience" },
  { text: "Projects", href: "#projects" },
  { text: "Contact", href: "#contact" },
];

const activeSection = ref("#home");
const isMenuOpen = ref(false);

const toggleMenu = () => (isMenuOpen.value = !isMenuOpen.value);

const scrollToSection = (hash) => {
  const el = document.querySelector(hash);
  if (!el) return;

  const top = el.getBoundingClientRect().top + window.scrollY - 80;

  window.scrollTo({ top, behavior: "smooth" });
};

/* =========================
   SCROLL SPY
========================= */
const handleScroll = () => {
  const sections = links.map(l => document.querySelector(l.href));

  for (let sec of sections) {
    if (!sec) continue;

    const rect = sec.getBoundingClientRect();

    if (rect.top <= 120 && rect.bottom >= 120) {
      activeSection.value = `#${sec.id}`;
      break;
    }
  }
};

/* =========================
   COUNTER
========================= */
const animateCounter = (id, target) => {
  let count = 0;

  const step = Math.ceil(target / 40);

  const interval = setInterval(() => {
    count += step;

    if (count >= target) {
      count = target;
      clearInterval(interval);
    }

    const el = document.getElementById(id);
    if (el) el.innerText = count;
  }, 30);
};

/* =========================
   DATA
========================= */
const experiences = [
  {
    role: "Software Developer",
    company: "Computers for Africa",
    period: "2025 - Present",
    description:
      "ERP systems, AWS deployments, and backend services for enterprise operations.",
  },
  {
    role: "Software Systems Developer",
    company: "USAID eLMIS",
    period: "2023 - 2025",
    description:
      "Supply chain systems, APIs, and data integration platforms.",
  },
  {
    role: "IT Support / Networking",
    company: "Various Organizations",
    period: "2022 - Present",
    description:
      "Networking, troubleshooting, and IT infrastructure support.",
  },
];

const state = reactive({
  projects: [
    {
      title: "Construction App",
      description: "RBAC system + project tracking",
      image: "/construction.png",
    },
    {
      title: "Supply Chain System",
      description: "Inventory + logistics platform",
      image: "/DHIS2.png",
    },
  ],
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

.font-coder {
  font-family: 'Press Start 2P', cursive;
}

/* =========================
   GLOBAL FEEL
========================= */
* {
  scroll-behavior: smooth;
}

/* =========================
   BUTTONS (UPGRADED)
========================= */
.btn-primary {
  @apply px-6 py-3 rounded-full font-semibold transition-all duration-300;
  background: linear-gradient(135deg, #22d3ee, #a855f7);
  box-shadow: 0 10px 25px rgba(34, 211, 238, 0.25);
}

.btn-primary:hover {
  transform: translateY(-2px) scale(1.03);
  box-shadow: 0 15px 35px rgba(159, 163, 163, 0.4);
}

.btn-primary:active {
  transform: scale(0.97);
}

.btn-outline {
  @apply px-6 py-3 rounded-full border border-white/20 transition-all duration-300;
}

.btn-outline:hover {
  border-color: #22d3ee;
  background: rgba(34, 211, 238, 0.05);
}

/* =========================
   SIDEBAR LINKS (🔥 KEY)
========================= */
.sidebar-link {
  @apply block text-gray-400 transition-all duration-300 relative text-sm tracking-wide;
}

.sidebar-link:hover {
  @apply text-white;
}

.sidebar-link::before {
  content: "";
  position: absolute;
  left: -12px;
  top: 50%;
  transform: translateY(-50%) scaleY(0);
  width: 3px;
  height: 60%;
  background: linear-gradient(to bottom, #22d3ee, #a855f7);
  border-radius: 10px;
  transition: 0.3s;
}

.sidebar-link:hover::before {
  transform: translateY(-50%) scaleY(1);
}

/* active link (used with script) */
.sidebar-active {
  @apply text-cyan-400;
}

.sidebar-active::before {
  transform: translateY(-50%) scaleY(1);
}

/* =========================
   GLASS CARDS (REFINED)
========================= */
.glass-card {
  @apply bg-white/5 backdrop-blur-xl border border-white/10 p-6 rounded-2xl transition-all duration-300;
}

.glass-card:hover {
  background: rgba(255, 255, 255, 0.08);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
  transform: translateY(-4px);
}

/* =========================
   PROJECT CARDS
========================= */
.project-card {
  @apply bg-[#111827] rounded-2xl overflow-hidden border border-white/10 transition-all duration-300;
}

.project-card:hover {
  transform: translateY(-6px) scale(1.01);
  box-shadow: 0 0 40px rgba(34, 211, 238, 0.2);
}

.project-img {
  @apply w-full h-48 object-cover transition duration-500;
}

.project-card:hover .project-img {
  transform: scale(1.05);
}

.project-link {
  @apply inline-block mt-4 text-cyan-400 transition;
}

.project-link:hover {
  @apply underline;
}

/* =========================
   SKILLS
========================= */
.skill-pill {
  @apply flex items-center px-5 py-2 rounded-full bg-white/5 border border-white/10 text-sm transition-all duration-300;
}

.skill-pill:hover {
  background: rgba(34, 211, 238, 0.15);
  transform: translateY(-2px);
}

/* =========================
   STATS
========================= */
.stat-card {
  @apply bg-white/5 border border-white/10 p-6 rounded-xl text-center transition;
}

.stat-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.4);
}

.stat-number {
  @apply text-3xl font-bold text-cyan-400;
}

/* =========================
   INPUTS (UPGRADED UX)
========================= */
.input {
  @apply w-full px-4 py-3 rounded-lg bg-white/5 border border-white/10 text-white transition-all duration-300;
}

.input:focus {
  outline: none;
  border-color: #22d3ee;
  box-shadow: 0 0 0 2px rgba(34, 211, 238, 0.3);
  background: rgba(255, 255, 255, 0.08);
}

/* =========================
   TITLES
========================= */
.section-title {
  @apply text-3xl lg:text-5xl font-extrabold;
  background: linear-gradient(to right, #22d3ee, #a855f7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* =========================
   SCROLLBAR (🔥 NICE TOUCH)
========================= */
::-webkit-scrollbar {
  width: 6px;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(#22d3ee, #a855f7);
  border-radius: 10px;
}

/* =========================
   SMALL ANIMATIONS
========================= */
.fade-in {
  animation: fadeIn 0.8s ease forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>