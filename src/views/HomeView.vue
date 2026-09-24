<template>
  <div class="portfolio-shell">
    <aside class="desktop-rail">
      <div class="rail-orb rail-orb-one"></div>
      <div class="rail-orb rail-orb-two"></div>
      <div class="rail-content">
        <a href="#home" class="brand" @click.prevent="scrollToSection('#home')"
          ><span class="brand-mark">CK</span><span>Chile Kasoka</span></a
        >
        <div class="profile-block">
          <div class="portrait-wrap">
            <img src="/stunna.jpg" alt="Chilekesha Kasoka" />
          </div>
          <p class="eyebrow">Computer Systems Engineer</p>
          <h1>Building systems that <em>work.</em></h1>
          <p class="profile-copy">
            Backend engineer with a systems mindset, based in Lusaka, Zambia.
          </p>
        </div>
        <nav class="rail-nav" aria-label="Portfolio sections">
          <a
            v-for="(link, index) in links"
            :key="link.href"
            :href="link.href"
            :class="{ active: activeSection === link.href }"
            @click.prevent="scrollToSection(link.href)"
            ><span>0{{ index + 1 }}</span
            >{{ link.text }}</a
          >
        </nav>
        <div class="rail-bottom">
          <div class="availability"><i></i> Available for select work</div>
          <div class="rail-socials">
            <a
              href="https://github.com/ChileKasoka"
              target="_blank"
              rel="noopener"
              >GitHub ↗</a
            ><a
              href="https://www.linkedin.com/in/chile-kasoka-402708195/"
              target="_blank"
              rel="noopener"
              >LinkedIn ↗</a
            >
          </div>
          <small>© {{ year }} Chile Kasoka</small>
        </div>
      </div>
    </aside>
    <header class="mobile-bar">
      <a href="#home" class="brand" @click.prevent="scrollToSection('#home')"
        ><span class="brand-mark">CK</span><span>Chile</span></a
      ><button
        class="menu-button"
        type="button"
        :aria-expanded="isMenuOpen"
        @click="isMenuOpen = !isMenuOpen"
      >
        {{ isMenuOpen ? "Close" : "Menu" }}
      </button>
    </header>
    <div v-if="isMenuOpen" class="mobile-menu">
      <a
        v-for="link in links"
        :key="link.href"
        :href="link.href"
        @click.prevent="
          scrollToSection(link.href);
          isMenuOpen = false;
        "
        >{{ link.text }}</a
      >
    </div>
    <main>
      <section id="home" class="hero section-pad">
        <div class="hero-grid"></div>
        <p class="section-kicker">01 — Hello, I’m Chile</p>
        <div class="hero-content">
          <div>
            <h2>Engineering <span>useful</span><br />digital systems.</h2>
            <p class="hero-lede">
              I design reliable software, APIs, and infrastructure for teams
              that need their technology to do more.
            </p>
            <div class="hero-actions">
              <a
                href="#contact"
                class="button button-primary"
                @click.prevent="scrollToSection('#contact')"
                >Let’s work together <span>↗</span></a
              ><a
                href="/Chilekesha_Kasoka_CV_2026.pdf"
                download
                class="button button-quiet"
                >Download CV <span>↓</span></a
              >
            </div>
          </div>
          <div class="hero-side-note">
            <div>
              <span>Currently</span>
              <strong>IT Officer<br />@ Phoenix of Zambia Assurance</strong>
            </div>
            <img
              class="employer-logo"
              src="/cropped-zambia-logo-phoenix.png"
              alt="Phoenix of Zambia Assurance"
            />
          </div>
        </div>
        <div class="hero-meta">
          <span>Scroll to explore</span><i></i
          ><span>Lusaka, Zambia · 2026</span>
        </div>
      </section>
      <section id="about" class="section-pad split-section">
        <div>
          <p class="section-kicker">02 — About</p>
          <h2 class="display-title">
            Technical depth.<br /><span>Human focus.</span>
          </h2>
        </div>
        <div class="about-copy">
          <p class="large-copy">
            I’m a computer systems engineer and backend-focused developer who
            turns complex requirements into maintainable, production-ready
            systems.
          </p>
          <p>
            I work across the full path from architecture and APIs to cloud
            deployment, databases, networking, and operational support. The goal
            is always the same: secure, efficient technology that solves a real
            problem.
          </p>
          <div class="stats-grid">
            <div>
              <strong>5<span>+</span></strong
              ><small>Years building Systems/Offering IT support </small>
            </div>
            <div>
              <strong>12<span>+</span></strong
              ><small>Projects delivered</small>
            </div>
            <div>
              <strong>7<span>+</span></strong
              ><small>Teams supported</small>
            </div>
          </div>
        </div>
      </section>
      <section id="experience" class="section-pad experience-section">
        <p class="section-kicker">03 — Experience</p>
        <h2 class="display-title">A record of <span>shipping.</span></h2>
        <div class="timeline">
          <article
            v-for="job in experiences"
            :key="job.role"
            class="timeline-item"
          >
            <p class="timeline-period">{{ job.period }}</p>
            <div>
              <h3>{{ job.role }}</h3>
              <p class="company">{{ job.company }}</p>
            </div>
            <p>{{ job.description }}</p>
          </article>
        </div>
      </section>
      <section id="projects" class="section-pad projects-section">
        <div class="section-heading">
          <div>
            <p class="section-kicker">04 — Selected work</p>
            <h2 class="display-title">Projects with <span>purpose.</span></h2>
          </div>
          <div class="project-controls">
            <button @click="prevProject" aria-label="Previous project">←</button
            ><span
              >{{ String(currentProject + 1).padStart(2, "0") }} /
              {{ String(projects.length).padStart(2, "0") }}</span
            ><button @click="nextProject" aria-label="Next project">→</button>
          </div>
        </div>
        <article class="featured-project">
          <div class="project-visual">
            <img
              :src="projects[currentProject].image"
              :alt="projects[currentProject].title"
            />
            <div class="project-number">0{{ currentProject + 1 }}</div>
          </div>
          <div class="project-detail">
            <p class="project-label">Featured project</p>
            <h3>{{ projects[currentProject].title }}</h3>
            <p>{{ projects[currentProject].description }}</p>
            <ul>
              <li
                v-for="detail in projects[currentProject].details"
                :key="detail"
              >
                {{ detail }}
              </li>
            </ul>
            <div class="tech-list">
              <span v-for="tech in projects[currentProject].tech" :key="tech">{{
                tech
              }}</span>
            </div>
            <a
              :href="projects[currentProject].link"
              target="_blank"
              rel="noopener"
              class="text-link"
              >View project <span>↗</span></a
            >
          </div>
        </article>
      </section>
      <section id="services" class="section-pad services-section">
        <p class="section-kicker">05 — What I do</p>
        <div class="section-heading">
          <h2 class="display-title">
            Built for the<br /><span>real world.</span>
          </h2>
          <p class="section-intro">
            From first sketch to steady operations, I bring the engineering
            coverage needed to build and sustain dependable products.
          </p>
        </div>
        <div class="services-grid">
          <article
            v-for="(service, index) in services"
            :key="service.title"
            class="service-card"
          >
            <span>0{{ index + 1 }}</span>
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
            <ul>
              <li v-for="item in service.items" :key="item">{{ item }}</li>
            </ul>
          </article>
        </div>
      </section>
      <section id="contact" class="contact-section section-pad">
        <div class="contact-glow"></div>
        <p class="section-kicker">06 — Contact</p>
        <div class="contact-grid">
          <div>
            <h2>
              Have a complex problem?<br /><span>Let’s make it clear.</span>
            </h2>
            <p>
              I’m open to collaborations, freelance work, and opportunities
              where thoughtful engineering can make a difference.
            </p>
            <a href="mailto:kasoka.chile@gmail.com" class="email-link"
              >kasoka.chile@gmail.com <span>↗</span></a
            >
            <div class="contact-details">
              <span>Lusaka, Zambia</span><span>+260 976 052 381</span>
            </div>
          </div>
          <form class="contact-form" @submit.prevent="handleSubmit">
            <label
              >Your name<input
                v-model="form.name"
                required
                placeholder="How should I call you?" /></label
            ><label
              >Email address<input
                v-model="form.email"
                required
                type="email"
                placeholder="name@company.com" /></label
            ><label
              >How can I help?<textarea
                v-model="form.message"
                required
                rows="4"
                placeholder="Tell me a little about your project"
              ></textarea></label
            ><button class="button button-primary" :disabled="loading">
              {{ loading ? "Sending…" : "Send message" }} <span>↗</span>
            </button>
            <p v-if="submitted" class="form-success">
              Thanks — your message has been sent.
            </p>
          </form>
        </div>
      </section>
      <footer>
        <span>Chile Kasoka</span><span>Designed & built with care</span
        ><a href="#home" @click.prevent="scrollToSection('#home')"
          >Back to top ↑</a
        >
      </footer>
    </main>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue";
const links = [
  { text: "Home", href: "#home" },
  { text: "About", href: "#about" },
  { text: "Experience", href: "#experience" },
  { text: "Projects", href: "#projects" },
  { text: "Services", href: "#services" },
  { text: "Contact", href: "#contact" },
];
const activeSection = ref("#home"),
  isMenuOpen = ref(false),
  currentProject = ref(0),
  form = ref({ name: "", email: "", message: "" }),
  loading = ref(false),
  submitted = ref(false),
  year = new Date().getFullYear();
const experiences = [
  {
    role: "IT Officer",
    company: "Phoenix of Zambia Assurance",
    period: "2026 — Present",
    description:
      "Overseeing IT infrastructure, systems administration, network operations, technical support, cloud services, and cybersecurity while ensuring the availability, reliability, and security of technology across the organization.",
  },
  {
    role: "Software Developer",
    company: "Computers for Africa",
    period: "2025 — 2026",
    description:
      "Building ERP systems, AWS deployments, and backend services for enterprise operations and construction management.",
  },
  {
    role: "Software Systems Developer",
    company: "USAID eLMIS",
    period: "2023 — 2025",
    description:
      "Developed supply-chain systems, APIs, and data integration platforms supporting Zambia’s national health sector.",
  },
  {
    role: "IT Support & Networking",
    company: "Various Organizations",
    period: "2022 — Present",
    description:
      "Designed, maintained, and troubleshot network environments and day-to-day IT infrastructure.",
  },
  {
    role: "Software Developer / Tester",
    company: "Adanian Labs",
    period: "2022",
    description:
      "Developed, tested, and deployed LetsTwende, a platform connecting customers and service providers.",
  },
];
const projects = [
  {
    title: "Construction Management App",
    description:
      "A full-scale system for managing construction projects, teams, and workflows.",
    image: "/construction.png",
    link: "https://github.com/ChileKasoka/csm",
    tech: ["Golang", "Vue.js", "PostgreSQL"],
    details: [
      "Role-based access control",
      "Project and task management",
      "Scalable REST API",
    ],
  },
  {
    title: "USAID Supply Chain System",
    description:
      "An enterprise supply-chain platform for tracking inventory, suppliers, and national health data.",
    image: "/openlmis.webp",
    link: "https://zm-elmis.org/",
    tech: ["Spring Boot", "PostgreSQL", "DHIS2"],
    details: [
      "Inventory and order tracking",
      "Reporting dashboards",
      "National system integration",
    ],
  },
  {
    title: "Church Management System",
    description:
      "An ERP-style system for managing church operations and administration.",
    image: "/shield.webp",
    link: "https://sci-eld.org/",
    tech: ["Vue.js", "Node.js", "MySQL"],
    details: [
      "Membership management",
      "Finance and reporting",
      "Multi-user roles",
    ],
  },
  {
    title: "LetsTwende Service Platform",
    description:
      "A platform that connects customers to trusted providers across many service categories.",
    image: "/letstwende.png",
    link: "https://letstwende.com/",
    tech: ["Vue.js", "Node.js", "MongoDB"],
    details: [
      "Customer-provider matching",
      "Bookings and notifications",
      "Growth-ready architecture",
    ],
  },
];
const services = [
  {
    title: "Backend Development",
    description: "Secure, scalable services built around clean architecture.",
    items: ["REST APIs", "RBAC & authentication", "Microservices"],
  },
  {
    title: "Full Stack Development",
    description:
      "End-to-end web applications designed to feel as good as they perform.",
    items: ["Vue.js applications", "System integration", "Database design"],
  },
  {
    title: "Mobile App Development",
    description:
      "Cross-platform mobile experiences made with modern, maintainable tools.",
    items: ["React Native", "Flutter", "UI / UX design"],
  },
  {
    title: "Hosting & DNS",
    description:
      "Well-configured web environments, domains, certificates, and email.",
    items: ["SSL certificates", "Reverse proxying", "Email servers"],
  },
  {
    title: "Cloud & DevOps",
    description:
      "Repeatable deployments and dependable operating environments.",
    items: ["AWS deployment", "Docker", "Server configuration"],
  },
  {
    title: "Infrastructure",
    description: "Practical network and IT foundations that teams can trust.",
    items: [
      "LAN / WAN setup",
      "Network troubleshooting",
      "Security configuration",
    ],
  },
  {
    title: "Database Management",
    description:
      "Fast, secure data systems shaped around the needs of the product.",
    items: ["PostgreSQL / MySQL", "Query optimisation", "Backup & recovery"],
  },
  {
    title: "Technical Support",
    description:
      "Ongoing systems care to keep people productive and services available.",
    items: ["System troubleshooting", "User support", "Performance monitoring"],
  },
];
const scrollToSection = (hash) =>
  document
    .querySelector(hash)
    ?.scrollIntoView({ behavior: "smooth", block: "start" });
const nextProject = () => {
  currentProject.value = (currentProject.value + 1) % projects.length;
};
const prevProject = () => {
  currentProject.value =
    (currentProject.value - 1 + projects.length) % projects.length;
};
const handleScroll = () => {
  for (const link of links) {
    const section = document.querySelector(link.href);
    if (section) {
      const rect = section.getBoundingClientRect();
      if (rect.top <= 160 && rect.bottom > 160) {
        activeSection.value = link.href;
        break;
      }
    }
  }
};
const handleSubmit = async () => {
  loading.value = true;
  submitted.value = false;
  try {
    await fetch("https://formspree.io/f/xnnbwypj", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(form.value),
    });
    form.value = { name: "", email: "", message: "" };
    submitted.value = true;
  } finally {
    loading.value = false;
  }
};
onMounted(() =>
  window.addEventListener("scroll", handleScroll, { passive: true }),
);
onUnmounted(() => window.removeEventListener("scroll", handleScroll));
</script>

<style scoped>
.portfolio-shell {
  --ink: #111827;
  --muted: #667085;
  --line: #e5e7eb;
  --lime: #c9f25c;
  --navy: #101a2d;
  background: #f8fafc;
  color: var(--ink);
  min-height: 100vh;
}
.desktop-rail {
  position: fixed;
  inset: 0 auto 0 0;
  width: 20rem;
  height: 100vh;
  overflow: hidden;
  background: var(--navy);
  color: #fff;
  z-index: 20;
}
.rail-content {
  position: relative;
  z-index: 1;
  height: 100%;
  padding: 2rem;
  display: flex;
  flex-direction: column;
}
.rail-orb {
  position: absolute;
  border-radius: 999px;
  filter: blur(8px);
  opacity: 0.36;
}
.rail-orb-one {
  width: 19rem;
  height: 19rem;
  right: -10rem;
  top: -7rem;
  background: #4f46e5;
}
.rail-orb-two {
  width: 13rem;
  height: 13rem;
  left: -8rem;
  bottom: 5rem;
  background: #b7ef4e;
}
.brand {
  display: flex;
  align-items: center;
  gap: 0.7rem;
  color: inherit;
  text-decoration: none;
  font-size: 0.82rem;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}
.brand-mark {
  width: 2.25rem;
  height: 2.25rem;
  border: 1px solid currentColor;
  border-radius: 50%;
  display: grid;
  place-items: center;
  font-size: 0.66rem;
  letter-spacing: 0;
}
.profile-block {
  margin-top: clamp(2.25rem, 7vh, 5rem);
}
.portrait-wrap {
  width: 5.8rem;
  height: 5.8rem;
  padding: 0.25rem;
  border: 1px solid rgba(255, 255, 255, 0.25);
  border-radius: 50%;
  margin-bottom: 1.25rem;
}
.portrait-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  filter: grayscale(20%);
}
.eyebrow,
.section-kicker,
.project-label {
  font-size: 0.68rem;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  font-weight: 800;
  color: #8190a9;
}
.profile-block .eyebrow {
  color: var(--lime);
}
.profile-block h1 {
  font-size: 1.75rem;
  line-height: 1.08;
  margin: 0.65rem 0 0.8rem;
  letter-spacing: -0.06em;
}
.profile-block h1 em {
  font-family: Georgia, serif;
  font-weight: 400;
}
.profile-copy {
  font-size: 0.82rem;
  line-height: 1.55;
  color: #b4bfd2;
  max-width: 14rem;
}
.rail-nav {
  margin-top: clamp(2rem, 6vh, 4rem);
  display: grid;
  gap: 0.65rem;
}
.rail-nav a {
  color: #9dacbf;
  text-decoration: none;
  font-size: 0.78rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  transition: 0.2s;
}
.rail-nav a span {
  font-size: 0.59rem;
  color: #65738a;
}
.rail-nav a:hover,
.rail-nav a.active {
  color: #fff;
}
.rail-nav a.active:after {
  content: "";
  width: 1.7rem;
  height: 1px;
  background: var(--lime);
  margin-left: auto;
}
.rail-bottom {
  margin-top: auto;
  font-size: 0.7rem;
  color: #95a4ba;
}
.availability {
  color: #d9e9c5;
  font-size: 0.67rem;
  margin-bottom: 1rem;
}
.availability i {
  display: inline-block;
  width: 0.45rem;
  height: 0.45rem;
  border-radius: 50%;
  background: var(--lime);
  margin-right: 0.4rem;
  box-shadow: 0 0 0 4px rgba(201, 242, 92, 0.12);
}
.rail-socials {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
}
.rail-socials a {
  color: #fff;
  text-decoration: none;
}
.mobile-bar,
.mobile-menu {
  display: none;
}
main {
  margin-left: 20rem;
  overflow: hidden;
}
.section-pad {
  padding: clamp(5rem, 9vw, 9rem) clamp(1.5rem, 6vw, 7rem);
}
.hero {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  flex-direction: column;
  position: relative;
  background: #fff;
  isolation: isolate;
}
.hero-grid {
  position: absolute;
  inset: 0;
  z-index: -1;
  opacity: 0.6;
  background-image:
    linear-gradient(#eef1f5 1px, transparent 1px),
    linear-gradient(90deg, #eef1f5 1px, transparent 1px);
  background-size: 4rem 4rem;
  mask-image: linear-gradient(to bottom, black 20%, transparent 85%);
}
.hero h2,
.display-title {
  font-size: clamp(3rem, 6.6vw, 7rem);
  line-height: 0.93;
  letter-spacing: -0.075em;
  font-weight: 700;
  margin: 1rem 0 1.75rem;
}
.hero h2 span,
.display-title span,
.contact-grid h2 span {
  font-family: Georgia, serif;
  font-weight: 400;
  font-style: italic;
  color: #53637a;
}
.hero-content {
  display: flex;
  align-items: end;
  justify-content: space-between;
  gap: 2rem;
}
.hero-lede {
  max-width: 34rem;
  font-size: 1.08rem;
  line-height: 1.7;
  color: #516074;
}
.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  margin-top: 2rem;
}
.button {
  display: inline-flex;
  align-items: center;
  gap: 1.5rem;
  padding: 0.85rem 1.1rem;
  border: 1px solid var(--ink);
  font:
    700 0.78rem "Space Grotesk",
    sans-serif;
  letter-spacing: 0.03em;
  text-decoration: none;
  cursor: pointer;
  transition: 0.2s;
}
.button-primary {
  background: var(--ink);
  color: #fff;
}
.button-primary:hover {
  background: #2b3c57;
  transform: translateY(-2px);
}
.button-quiet {
  color: var(--ink);
  background: #fff;
}
.button-quiet:hover {
  background: #f1f5f9;
}
.hero-side-note {
  border-left: 1px solid #ced5df;
  padding-left: 1rem;
  min-width: 17rem;
  font-size: 0.75rem;
  line-height: 1.6;
  display: flex;
  align-items: center;
  gap: 1rem;
}
.hero-side-note span {
  display: block;
  color: #7d8ba0;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  font-size: 0.62rem;
  margin-bottom: 0.4rem;
}
.employer-logo {
  width: 6rem;
  max-height: 6rem;
  object-fit: contain;
  flex: 0 0 auto;
}
.hero-meta {
  position: absolute;
  bottom: 2rem;
  left: clamp(1.5rem, 6vw, 7rem);
  right: clamp(1.5rem, 6vw, 7rem);
  display: flex;
  align-items: center;
  gap: 0.8rem;
  color: #7d8ba0;
  font-size: 0.64rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.hero-meta i {
  height: 1px;
  background: #d9dfe8;
  flex: 1;
}
.split-section {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(20rem, 0.9fr);
  gap: 5rem;
  background: #eef2f6;
}
.about-copy {
  padding-top: 2rem;
}
.large-copy {
  font-size: 1.35rem;
  line-height: 1.45;
  font-weight: 600;
  letter-spacing: -0.025em;
}
.about-copy > p:not(.large-copy) {
  color: var(--muted);
  line-height: 1.75;
  margin-top: 1.25rem;
}
.stats-grid {
  margin-top: 3rem;
  padding-top: 1.5rem;
  border-top: 1px solid #d6dde5;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
.stats-grid strong {
  display: block;
  font-size: 2.3rem;
  letter-spacing: -0.07em;
}
.stats-grid strong span {
  color: #778aa2;
}
.stats-grid small {
  font-size: 0.68rem;
  color: #69788e;
}
.experience-section {
  background: #fff;
}
.timeline {
  margin-top: 3.5rem;
  border-top: 1px solid var(--line);
}
.timeline-item {
  display: grid;
  grid-template-columns: 0.6fr 1fr 1.4fr;
  gap: 1.5rem;
  padding: 1.8rem 0;
  border-bottom: 1px solid var(--line);
}
.timeline-period {
  font-size: 0.74rem;
  color: #728198;
}
.timeline-item h3 {
  font-size: 1rem;
  letter-spacing: -0.02em;
}
.company {
  font-size: 0.78rem;
  color: #5d6d83;
  margin-top: 0.35rem;
}
.timeline-item > p:last-child {
  font-size: 0.82rem;
  line-height: 1.65;
  color: #65748a;
}
.projects-section {
  background: var(--navy);
  color: #f9fafb;
}
.projects-section .section-kicker {
  color: #9aabc1;
}
.projects-section .display-title span {
  color: #c6d1e0;
}
.section-heading {
  display: flex;
  justify-content: space-between;
  align-items: end;
  gap: 2rem;
}
.project-controls {
  display: flex;
  gap: 0.75rem;
  align-items: center;
  font-size: 0.7rem;
  color: #b4c0d1;
}
.project-controls button {
  border: 1px solid #47566b;
  background: transparent;
  color: white;
  width: 2.35rem;
  height: 2.35rem;
  cursor: pointer;
}
.project-controls button:hover {
  border-color: var(--lime);
  color: var(--lime);
}
.featured-project {
  display: grid;
  grid-template-columns: 1.15fr 0.85fr;
  margin-top: 3.5rem;
  border: 1px solid #283750;
  background: #142239;
}
.project-visual {
  min-height: 30rem;
  position: relative;
  overflow: hidden;
}
.project-visual:after {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(15, 26, 45, 0.1),
    rgba(15, 26, 45, 0.5)
  );
}
.project-visual img {
  width: 100%;
  height: 100%;
  position: absolute;
  object-fit: cover;
  transition: transform 0.6s;
}
.featured-project:hover img {
  transform: scale(1.04);
}
.project-number {
  position: absolute;
  z-index: 1;
  top: 1.3rem;
  left: 1.3rem;
  color: var(--lime);
  font-size: 0.75rem;
  letter-spacing: 0.12em;
}
.project-detail {
  padding: 3rem;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.project-detail h3 {
  font-size: 2.3rem;
  line-height: 1;
  letter-spacing: -0.06em;
  margin: 1rem 0;
}
.project-detail > p:not(.project-label) {
  color: #b9c3d2;
  font-size: 0.9rem;
  line-height: 1.7;
}
.project-detail ul {
  margin: 1.5rem 0;
  padding: 0;
  list-style: none;
  color: #dfe6f1;
  font-size: 0.78rem;
  line-height: 2;
}
.project-detail li:before {
  content: "—";
  color: var(--lime);
  margin-right: 0.5rem;
}
.tech-list {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
  margin-top: auto;
}
.tech-list span {
  border: 1px solid #41516a;
  color: #b9c7d8;
  padding: 0.38rem 0.55rem;
  font-size: 0.64rem;
}
.text-link {
  margin-top: 1.5rem;
  color: var(--lime);
  font-size: 0.78rem;
  font-weight: 700;
  text-decoration: none;
}
.text-link span,
.email-link span {
  margin-left: 0.4rem;
}
.services-section {
  background: #f8fafc;
}
.section-intro {
  max-width: 21rem;
  font-size: 0.88rem;
  line-height: 1.7;
  color: #617087;
  margin-bottom: 2rem;
}
.services-grid {
  margin-top: 3.5rem;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  border-top: 1px solid #dce2e9;
  border-left: 1px solid #dce2e9;
}
.service-card {
  min-height: 17rem;
  padding: 1.6rem;
  border-right: 1px solid #dce2e9;
  border-bottom: 1px solid #dce2e9;
  transition: 0.25s;
}
.service-card:hover {
  background: #fff;
  box-shadow: 0 1rem 2rem rgba(26, 40, 60, 0.06);
}
.service-card > span {
  font-size: 0.65rem;
  color: #8492a5;
}
.service-card h3 {
  font-size: 1.05rem;
  letter-spacing: -0.03em;
  margin: 2.2rem 0 0.65rem;
}
.service-card p {
  font-size: 0.78rem;
  line-height: 1.65;
  color: #66758b;
}
.service-card ul {
  margin: 1.1rem 0 0;
  padding: 0;
  list-style: none;
  font-size: 0.69rem;
  color: #26364d;
  line-height: 1.9;
}
.service-card li:before {
  content: "•";
  color: #90aa4d;
  margin-right: 0.4rem;
}
.contact-section {
  position: relative;
  color: #fff;
  background: #17243a;
  overflow: hidden;
}
.contact-glow {
  position: absolute;
  width: 42rem;
  height: 42rem;
  right: -20rem;
  bottom: -24rem;
  border-radius: 50%;
  background: #5b45cf;
  filter: blur(70px);
  opacity: 0.35;
}
.contact-section .section-kicker {
  position: relative;
  color: #bdc9d9;
}
.contact-grid {
  position: relative;
  display: grid;
  grid-template-columns: 1fr 0.8fr;
  gap: 5rem;
  margin-top: 1.25rem;
}
.contact-grid h2 {
  font-size: clamp(2.5rem, 4.6vw, 5rem);
  line-height: 0.97;
  letter-spacing: -0.07em;
}
.contact-grid h2 span {
  color: #cbd6e5;
}
.contact-grid > div > p {
  max-width: 31rem;
  line-height: 1.7;
  color: #c5cfdd;
  font-size: 0.9rem;
  margin: 1.5rem 0;
}
.email-link {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--lime);
  text-decoration: none;
  letter-spacing: -0.035em;
}
.contact-details {
  display: flex;
  gap: 1.2rem;
  margin-top: 2.5rem;
  font-size: 0.7rem;
  color: #aab8cb;
}
.contact-form {
  display: grid;
  gap: 1rem;
}
.contact-form label {
  font-size: 0.65rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #aebbd0;
}
.contact-form input,
.contact-form textarea {
  display: block;
  width: 100%;
  margin-top: 0.45rem;
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid #4b5a6f;
  color: #fff;
  padding: 0.8rem;
  font:
    400 0.84rem "Space Grotesk",
    sans-serif;
  resize: vertical;
}
.contact-form input:focus,
.contact-form textarea:focus {
  outline: 1px solid var(--lime);
  border-color: var(--lime);
}
.contact-form .button {
  justify-content: space-between;
  border-color: var(--lime);
  color: #162238;
  background: var(--lime);
  margin-top: 0.4rem;
}
.form-success {
  font-size: 0.75rem;
  color: var(--lime);
}
footer {
  background: #101a2d;
  color: #99a9bd;
  padding: 1.25rem clamp(1.5rem, 6vw, 7rem);
  font-size: 0.65rem;
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}
footer a {
  color: #fff;
  text-decoration: none;
}
@media (max-width: 1023px) {
  .desktop-rail {
    display: none;
  }
  main {
    margin-left: 0;
  }
  .mobile-bar {
    height: 4.5rem;
    padding: 0 1.25rem;
    background: #101a2d;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: fixed;
    inset: 0 0 auto;
    z-index: 20;
  }
  .mobile-bar .brand-mark {
    width: 2rem;
    height: 2rem;
  }
  .menu-button {
    border: 0;
    background: transparent;
    color: #fff;
    text-transform: uppercase;
    font:
      700 0.66rem "Space Grotesk",
      sans-serif;
    letter-spacing: 0.12em;
  }
  .mobile-menu {
    display: grid;
    position: fixed;
    z-index: 19;
    inset: 4.5rem 0 auto;
    background: #101a2d;
    padding: 1rem 1.25rem 1.5rem;
    border-top: 1px solid #26364d;
  }
  .mobile-menu a {
    color: #c4cfdd;
    text-decoration: none;
    padding: 0.55rem 0;
    font-size: 0.82rem;
  }
  .hero {
    padding-top: 8rem;
  }
  .section-pad {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
  .hero-content,
  .section-heading {
    align-items: flex-start;
  }
  .hero-side-note {
    display: none;
  }
  .split-section,
  .contact-grid {
    gap: 3rem;
  }
  .featured-project {
    grid-template-columns: 1fr;
  }
  .project-visual {
    min-height: 20rem;
  }
  .project-detail {
    padding: 2rem;
  }
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (max-width: 640px) {
  .hero {
    min-height: 42rem;
  }
  .hero h2,
  .display-title {
    font-size: clamp(2.8rem, 14vw, 4.2rem);
  }
  .hero-meta {
    bottom: 1.3rem;
  }
  .split-section,
  .contact-grid {
    grid-template-columns: 1fr;
  }
  .about-copy {
    padding-top: 0;
  }
  .stats-grid {
    gap: 0.65rem;
  }
  .stats-grid strong {
    font-size: 1.8rem;
  }
  .timeline-item {
    grid-template-columns: 1fr;
    gap: 0.45rem;
  }
  .timeline-item h3 {
    margin-top: 0.35rem;
  }
  .section-heading {
    display: block;
  }
  .project-controls {
    margin-top: 1.75rem;
  }
  .project-visual {
    min-height: 15rem;
  }
  .project-detail h3 {
    font-size: 1.85rem;
  }
  .services-grid {
    grid-template-columns: 1fr;
  }
  .service-card {
    min-height: auto;
  }
  .contact-details {
    flex-direction: column;
    gap: 0.5rem;
  }
  footer {
    flex-wrap: wrap;
    line-height: 1.6;
  }
}
</style>
