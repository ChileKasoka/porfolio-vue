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
<div class="lg:hidden fixed top-0 w-full bg-[#0f172a] border-b border-white/10 p-4 flex justify-between items-center z-50">

  <span class="font-bold text-white">$ ck</span>

  <div class="flex items-center gap-3">

    <!-- THEME TOGGLE -->
    <button
      @click="toggleTheme"
      class="px-3 py-1 rounded-full bg-gray-200 dark:bg-[#1e293b] text-xs font-semibold text-gray-800 dark:text-white"
    >
      {{ isDark ? "☀️" : "🌙" }}
    </button>

    <!-- MENU BUTTON -->
    <button @click="toggleMenu" class="text-white text-xl">
      ☰
    </button>

  </div>

</div>

    <!-- MOBILE MENU -->
<!-- MOBILE OVERLAY -->
<div
  v-if="isMenuOpen"
  class="lg:hidden fixed inset-0 bg-black/50 z-40"
  @click="toggleMenu"
></div>

<!-- MOBILE SIDEBAR (SLIDE IN) -->
<aside
  class="lg:hidden fixed top-0 left-0 h-full w-72 bg-[#0f172a] border-r border-white/10 p-6 z-50 transform transition-transform duration-300"
  :class="isMenuOpen ? 'translate-x-0' : '-translate-x-full'"
>

  <!-- Top -->
  <div>
    <div class="flex flex-col items-start text-left">

      <img
        src="/stunna.webp"
        loading="lazy"
        class="w-24 h-24 rounded-full border-4 border-cyan-500/40 shadow-[0_0_30px_rgba(34,211,238,0.4)]"
      />

      <h2 class="mt-4 text-lg font-bold text-white">
        Chilekesha Kasoka
      </h2>

      <p class="text-gray-400 text-sm">
        COMPUTER SYSTEMS ENGINEER
      </p>

    </div>

    <!-- NAV -->
    <nav class="mt-10 space-y-4">
      <a
        v-for="link in links"
        :key="link.href"
        @click="scrollToSection(link.href); toggleMenu()"
        :class="[
          'sidebar-link',
          activeSection === link.href ? 'sidebar-active' : ''
        ]"
      >
        {{ link.text }}
      </a>
    </nav>
  </div>

  <!-- Footer -->
  <div class="text-xs text-gray-500 mt-10">
    © {{ new Date().getFullYear() }}
  </div>

</aside>

    <!-- MAIN -->
<main class="w-full lg:ml-72 pt-20 lg:pt-0
             bg-white text-gray-900 
             dark:bg-[#0b0f19] dark:text-white 
             transition-colors duration-300">

      <!-- THEME TOGGLE -->
<div class="hidden lg:block fixed top-16 right-6 z-50">
  <button
    @click="toggleTheme"
    class="px-4 py-2 rounded-full 
           bg-gray-200 dark:bg-[#1e293b] 
           text-gray-900 dark:text-white 
           text-sm font-semibold shadow 
           hover:scale-105 transition"
  >
    {{ isDark ? "☀️" : "🌙" }}
  </button>
</div>

      <!-- HERO -->
      <section id="home" class="min-h-screen px-6 flex flex-col justify-start lg:pt-20">

        <h1 class="text-5xl lg:text-7xl font-extrabold">
          Hi, I’m <span class="gradient-text">Chile</span>
        </h1>

    <p class="mt-6 text-gray-700 dark:text-gray-300 max-w-3xl leading-relaxed">
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
      <section id="experience" class="min-h-screen px-6 py-24">

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
<section id="projects" class="px-6 min-h-screen flex flex-col justify-center">

  <h2 class="section-title">Projects</h2>

<div
  class="relative mt-10 max-w-5xl mx-auto w-full"
  @mouseenter="stopAutoplay"
  @mouseleave="startAutoplay"
>

    <!-- CARD -->
    <div class="project-card p-6 bg-white dark:bg-[#111827] border border-gray-200 dark:border-white/10">

      <img
        :src="state.projects[currentProject].image"
        class="project-img mb-6 rounded-xl"
      />

      <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">
        {{ state.projects[currentProject].title }}
      </h3>

      <p class="text-gray-600 dark:text-gray-300 mb-4">
        {{ state.projects[currentProject].description }}
      </p>

      <!-- DETAILS -->
      <ul class="text-sm text-gray-500 dark:text-gray-400 space-y-1 mb-4">
        <li v-for="(point, i) in state.projects[currentProject].details" :key="i">
          • {{ point }}
        </li>
      </ul>

      <!-- TECH -->
      <div class="flex flex-wrap gap-2 mt-4">
        <span
          v-for="(tech, i) in state.projects[currentProject].tech"
          :key="i"
          class="px-3 py-1 text-xs rounded-full border
                 bg-cyan-500/10 text-cyan-600 dark:text-cyan-400
                 border-cyan-300 dark:border-cyan-500/20"
        >
          {{ tech }}
        </span>
      </div>

      <!-- LINK -->
      <div class="mt-6">
        <a
          :href="state.projects[currentProject].link"
          target="_blank"
          class="btn-primary"
        >
          View Project
        </a>
      </div>

    </div>

    <!-- CONTROLS -->
    <div class="flex justify-between items-center mt-6">

      <button
        @click="prevProject"
        class="btn-outline text-gray-700 dark:text-gray-300 border-gray-300 dark:border-white/20"
      >
        ← Prev
      </button>

      <!-- DOTS -->
      <div class="flex gap-2">
        <span
          v-for="(p, i) in state.projects"
          :key="i"
          @click="currentProject = i"
          class="w-3 h-3 rounded-full cursor-pointer transition"
          :class="i === currentProject
            ? 'bg-cyan-500'
            : 'bg-gray-300 dark:bg-gray-600'"
        ></span>
      </div>

      <button
        @click="nextProject"
        class="btn-outline text-gray-700 dark:text-gray-300 border-gray-300 dark:border-white/20"
      >
        Next →
      </button>

    </div>

  </div>

</section>

<section id="services" class="min-h-screen px-6 pt-24 flex flex-col justify-center">

  <h2 class="section-title">Services</h2>

  <p class="mt-4 text-gray-700 dark:text-gray-300 max-w-2xl">
    I provide a wide range of IT and software solutions—from backend development and system design 
    to networking, infrastructure, and technical support—helping businesses build, scale, and maintain reliable systems.
  </p>

  <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 mt-10">

    <!-- BACKEND -->
    <div class="glass-card hover:scale-[1.02] transition">
      <h3 class="text-xl font-bold text-cyan-500 dark:text-cyan-400">
        Backend Development
      </h3>
      <p class="mt-3 text-sm text-gray-600 dark:text-gray-300">
        Building secure, scalable APIs and systems using Golang, Spring Boot, and modern architectures.
      </p>
      <ul class="mt-4 text-sm text-gray-500 dark:text-gray-400 space-y-1">
        <li>• REST API Development</li>
        <li>• RBAC & Authentication Systems</li>
        <li>• Microservices Architecture</li>
        <li>• Performance Optimization</li>
      </ul>
    </div>

    <!-- FULL STACK -->
    <div class="glass-card hover:scale-[1.02] transition">
      <h3 class="text-xl font-bold text-cyan-500 dark:text-cyan-400">
        Full Stack Development
      </h3>
      <p class="mt-3 text-sm text-gray-600 dark:text-gray-300">
        End-to-end application development with modern frontend and backend technologies.
      </p>
      <ul class="mt-4 text-sm text-gray-500 dark:text-gray-400 space-y-1">
        <li>• Vue.js Frontend Apps</li>
        <li>• System Integration</li>
        <li>• Database Design</li>
        <li>• Responsive UI/UX</li>
      </ul>
    </div>

    <!-- CLOUD -->
    <div class="glass-card hover:scale-[1.02] transition">
      <h3 class="text-xl font-bold text-cyan-500 dark:text-cyan-400">
        Cloud & DevOps
      </h3>
      <p class="mt-3 text-sm text-gray-600 dark:text-gray-300">
        Deploying and managing scalable applications in cloud environments.
      </p>
      <ul class="mt-4 text-sm text-gray-500 dark:text-gray-400 space-y-1">
        <li>• AWS Deployment</li>
        <li>• Docker & Containerization</li>
        <li>• CI/CD Pipelines</li>
        <li>• Server Configuration</li>
      </ul>
    </div>

    <!-- NETWORKING -->
    <div class="glass-card hover:scale-[1.02] transition">
      <h3 class="text-xl font-bold text-cyan-500 dark:text-cyan-400">
        Networking & Infrastructure
      </h3>
      <p class="mt-3 text-sm text-gray-600 dark:text-gray-300">
        Designing and maintaining reliable network systems and IT infrastructure.
      </p>
      <ul class="mt-4 text-sm text-gray-500 dark:text-gray-400 space-y-1">
        <li>• LAN/WAN Setup</li>
        <li>• Router & Switch Configuration</li>
        <li>• Network Troubleshooting</li>
        <li>• Security Configuration</li>
      </ul>
    </div>

    <!-- IT SUPPORT -->
    <div class="glass-card hover:scale-[1.02] transition">
      <h3 class="text-xl font-bold text-cyan-500 dark:text-cyan-400">
        IT Support & Maintenance
      </h3>
      <p class="mt-3 text-sm text-gray-600 dark:text-gray-300">
        Providing ongoing support to ensure systems run smoothly and efficiently.
      </p>
      <ul class="mt-4 text-sm text-gray-500 dark:text-gray-400 space-y-1">
        <li>• System Troubleshooting</li>
        <li>• Hardware & Software Support</li>
        <li>• Performance Monitoring</li>
        <li>• User Support & Training</li>
      </ul>
    </div>

    <!-- DATABASE -->
    <div class="glass-card hover:scale-[1.02] transition">
      <h3 class="text-xl font-bold text-cyan-500 dark:text-cyan-400">
        Database Management
      </h3>
      <p class="mt-3 text-sm text-gray-600 dark:text-gray-300">
        Designing, optimizing, and maintaining secure and efficient databases.
      </p>
      <ul class="mt-4 text-sm text-gray-500 dark:text-gray-400 space-y-1">
        <li>• PostgreSQL / MySQL</li>
        <li>• Query Optimization</li>
        <li>• Data Modeling</li>
        <li>• Backup & Recovery</li>
      </ul>
    </div>

  </div>

</section>

<!-- CONTACT -->
<section id="contact" class="min-h-screen flex flex-col justify-center px-6 py-20">

  <h2 class="section-title text-center">Contact</h2>

  <div class="mt-10 grid lg:grid-cols-2 gap-10 max-w-6xl mx-auto w-full">

    <!-- CONTACT CARD -->
    <div class="glass-card p-6 bg-white dark:bg-[#111827] border border-gray-200 dark:border-white/10">

      <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-4">
        Get in Touch
      </h3>

      <p class="text-gray-600 dark:text-gray-300 text-sm leading-relaxed">
        Feel free to reach out for collaborations, freelance work, or any IT-related services. 
        I'm open to opportunities and always ready to solve real-world problems.
      </p>

      <!-- DETAILS -->
      <div class="mt-6 space-y-4 text-sm">

        <div>
          <p class="text-gray-500 dark:text-gray-400">Email</p>
          <p class="text-gray-900 dark:text-white font-medium">
            kasoka.chile@gmail.com
          </p>
        </div>

        <div>
          <p class="text-gray-500 dark:text-gray-400">Phone</p>
          <p class="text-gray-900 dark:text-white font-medium">
            +260 976 052 381
          </p>
        </div>

        <div>
          <p class="text-gray-500 dark:text-gray-400">Location</p>
          <p class="text-gray-900 dark:text-white font-medium">
            Lusaka, Zambia
          </p>
        </div>

      </div>

      <!-- SOCIAL -->
      <div class="mt-6">
        <SocialMedia />
      </div>

    </div>

    <!-- CONTACT FORM -->
    <form @submit.prevent="handleSubmit" class="space-y-4 w-full">

      <!-- NAME -->
      <input
        v-model="form.name"
        placeholder="Name"
        class="input border border-gray-400 dark:border-white/10
               bg-white dark:bg-white/5
               text-gray-900 dark:text-white
               placeholder-gray-500
               focus:border-cyan-500 dark:focus:border-cyan-400"
      />

      <!-- EMAIL -->
      <input
        v-model="form.email"
        placeholder="Email"
        class="input border border-gray-400 dark:border-white/10
               bg-white dark:bg-white/5
               text-gray-900 dark:text-white
               placeholder-gray-500
               focus:border-cyan-500 dark:focus:border-cyan-400"
      />

      <!-- COMPANY -->
      <input
        v-model="form.company"
        placeholder="Company"
        class="input border border-gray-400 dark:border-white/10
               bg-white dark:bg-white/5
               text-gray-900 dark:text-white
               placeholder-gray-500
               focus:border-cyan-500 dark:focus:border-cyan-400"
      />

      <!-- MESSAGE -->
      <textarea
        v-model="form.message"
        rows="4"
        placeholder="Message"
        class="input border border-gray-400 dark:border-white/10
               bg-white dark:bg-white/5
               text-gray-900 dark:text-white
               placeholder-gray-500
               focus:border-cyan-500 dark:focus:border-cyan-400"
      />

      <button class="btn-primary w-full">
        {{ loading ? "Sending..." : "Send Message" }}
      </button>

    </form>

  </div>

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
const isDark = ref(false);

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

  // DEFAULT = LIGHT MODE
  if (!saved) {
    isDark.value = false;
    document.documentElement.classList.remove("dark");
    localStorage.setItem("theme", "light");
  }

  // USER CHOSE DARK
  else if (saved === "dark") {
    isDark.value = true;
    document.documentElement.classList.add("dark");
  }

  // USER CHOSE LIGHT (or fallback)
  else {
    isDark.value = false;
    document.documentElement.classList.remove("dark");
  }

  // Scroll spy
  window.addEventListener("scroll", handleScroll);

  // Counters
  animateCounter("projects-complete", 12);
  animateCounter("experience-years", 4);
  animateCounter("clients", 5);

  // Carousel autoplay
  startAutoplay();
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
  stopAutoplay();
});

/* =========================
   FORM
========================= */
const form = ref({ name: "", email: "", company: "", message: "" });
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
  { text: "Services", href: "#services" },
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

const currentProject = ref(0);
let interval = null;

const nextProject = () => {
  currentProject.value =
    (currentProject.value + 1) % state.projects.length;
};

const prevProject = () => {
  currentProject.value =
    (currentProject.value - 1 + state.projects.length) %
    state.projects.length;
};

const startAutoplay = () => {
  stopAutoplay(); // prevent duplicates
  interval = setInterval(() => {
    nextProject();
  }, 4000);
};

const stopAutoplay = () => {
  if (interval) {
    clearInterval(interval);
    interval = null;
  }
};

const state = reactive({
  projects: [
    {
      title: "Construction Management App",
      description:
        "A full-scale system for managing construction projects, teams, and workflows.",
      image: "/construction.png",
      link: "https://github.com/ChileKasoka/csm",
      tech: ["Golang", "Vue.js", "PostgreSQL"],
      details: [
        "Role-based access control (RBAC) system",
        "Project and task management",
        "User-role assignment with permissions",
        "RESTful API with scalable architecture",
      ],
    },
    {
      title: "USAID Supply Chain System",
      description:
        "Enterprise supply chain platform for tracking inventory and suppliers.",
      image: "/DHIS2.png",
      link: "https://zm-elmis.org/",
      tech: ["Spring Boot", "PostgreSQL", "DHIS2"],
      details: [
        "Inventory and order tracking system",
        "Real-time reporting dashboards",
        "Data reliability and system optimization",
        "Integration with national health systems",
      ],
    },
    {
      title: "Church Management System",
      description:
        "ERP-style system for managing church operations and administration.",
      image: "/shield.webp",
      link: "https://sci-eld.org/",
      tech: ["Vue.js", "Node.js", "MySQL"],
      details: [
        "Membership management",
        "Finance and reporting modules",
        "Role-based user system",
        "Scalable multi-user system",
      ],
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
  @apply rounded-2xl overflow-hidden transition-all duration-300;
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