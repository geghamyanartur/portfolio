<script setup>
import { ref } from 'vue'
import ModalOverlay from './components/ModalOverlay.vue'

const showCv = ref(false)
const appBase = import.meta.env.BASE_URL || '/'
const cvUrl = new URL('Artur-CV.pdf', new URL(appBase, window.location.origin)).href

const experience = [
  {
    company: 'Esterox LLC',
    title: 'Frontend Developer',
    period: 'Jun 2025 – Nov 2025',
    points: [
      'Developed and maintained high-impact product features across two platforms, including funnel builder, community spaces, messaging, event flows, and analytics dashboards.',
      'Built scalable UI architectures using microfrontends and reusable component systems.',
      'Collaborated with cross-functional teams to deliver fast, responsive, and user-friendly experiences.',
    ],
    tech: ['Vue.js', 'Nuxt.js', 'Tailwind CSS', 'Microfrontends', 'REST APIs'],
  },
  {
    company: 'Fidem LLC',
    title: 'Full Stack Developer',
    period: 'Jun 2024 – Jun 2025',
    points: [
      'Developed and maintained a large-scale e-commerce platform using Vue, Nuxt, Laravel, and Bagisto.',
      'Integrated multiple payment methods and created custom business features.',
      'Ensured scalable and maintainable code across frontend and backend.',
    ],
    tech: ['Vue.js', 'Nuxt.js', 'Laravel', 'Bagisto', 'MySQL'],
  },
  {
    company: 'M&D Systems LLC',
    title: 'Full Stack Developer',
    period: 'Mar 2023 – Jun 2024',
    points: [
      'Worked on a large application “theshedapp” using Vue and Laravel.',
      'Built and consumed APIs, implemented new features, and integrated payment solutions.',
      'Maintained code quality and performance across the stack.',
    ],
    tech: ['Vue.js', 'Laravel', 'REST APIs', 'Payments'],
  },
  {
    company: 'Exio Tech',
    title: 'Frontend Blockchain Developer',
    period: 'Jan 2021 – Nov 2022',
    points: [
      'Developed landing pages and full websites using Nuxt.js.',
      'Integrated blockchain functionality using Web3.js for smart contract interactions.',
      'Contributed to blockchain-based projects from ideation to deployment.',
    ],
    tech: ['Nuxt.js', 'Web3.js', 'Solidity', 'Smart Contracts'],
  },
];

const projects = [
  {
    name: 'E-commerce Platform',
    type: 'Large-scale SaaS',
    description:
      'E-commerce platform built on Vue, Nuxt, Laravel, and Bagisto with multi-payment integration.',
    bullets: [
      'Custom product, cart, and checkout flows.',
      'Payment gateways integration and order handling.',
      'Reusable UI components and responsive layout.',
    ],
    tech: ['Vue.js', 'Nuxt.js', 'Laravel', 'Bagisto', 'MySQL', 'Docker'],
  },
  {
    name: 'TheShed App',
    type: 'Web Application',
    description:
      'Full stack app using Vue and Laravel with payment integration and complex business logic.',
    bullets: [
      'API-driven architecture with clean separation of concerns.',
      'Implemented new features based on business requirements.',
      'Optimized user flows and performance.',
    ],
    tech: ['Vue.js', 'Laravel', 'REST APIs'],
  },
  {
    name: 'Blockchain Landing & DApps',
    type: 'Web3 / Frontend',
    description:
      'Landing pages and DApp frontends interacting with smart contracts via Web3.js.',
    bullets: [
      'Wallet connection and on-chain interaction UX.',
      'Smart contract calls from Nuxt.js frontends.',
      'Modern UI with responsive layouts.',
    ],
    tech: ['Nuxt.js', 'Web3.js', 'Solidity'],
  },
];

const skillGroups = [
  {
    category: 'Frontend',
    items: ['HTML', 'CSS', 'Bootstrap', 'Tailwind', 'JavaScript', 'jQuery', 'Vue.js', 'Nuxt.js', 'Next.js'],
  },
  {
    category: 'Backend',
    items: ['PHP', 'Laravel', 'MySQL', 'GraphQL', 'Docker'],
  },
  {
    category: 'Blockchain',
    items: ['Solidity', 'Smart Contracts', 'Web3.js'],
  },
  {
    category: 'General',
    items: ['Technical Programming', 'Clean Code', 'Team Collaboration'],
  },
];

const education = [
  {
    name: 'Yerevan State College of Informatics',
    detail: '2014 – 2018',
  },
  {
    name: 'Exio Tech',
    detail: 'Web Development · 2021',
  },
  {
    name: 'Profit Development Company',
    detail: 'Web Development · 2020',
  },
];

const contacts = {
  name: 'Artur Geghamyan',
  role: 'Full Stack Web Developer',
  phone: '+374-44-147-477',
  email: 'geghamyan.artur.dev@gmail.com',
  linkedin: 'https://linkedin.com/in/arturgeghamyan', // you can replace with full URL
};
</script>

<template>
  <div class="page text-slate-100">
    <!-- NAVBAR -->
    <header
      class="sticky top-0 z-40 border-b border-slate-800/60 bg-slate-950/80 backdrop-blur"
    >
      <div class="mx-auto flex max-w-5xl items-center justify-between px-4 py-3">
        <div class="flex items-center gap-3">
          <div
            class="flex h-9 w-9 items-center justify-center rounded-xl bg-brand-600 text-sm font-semibold shadow-lg shadow-brand-500/40"
          >
            <img src="@/assets/images/photo2mb.jpg" alt="" class="rounded-full h-full w-full object-cover">
          </div>
          <div class="leading-tight">
            <div class="text-sm font-semibold">
              {{ contacts.name }}
            </div>
            <div class="text-xs text-slate-400">
              {{ contacts.role }}
            </div>
          </div>
        </div>
        <nav class="hidden items-center gap-5 text-xs md:flex">
          <a href="#about" class="hover:text-brand-400">About</a>
          <a href="#experience" class="hover:text-brand-400">Experience</a>
          <a href="#projects" class="hover:text-brand-400">Projects</a>
          <a href="#skills" class="hover:text-brand-400">Skills</a>
          <a href="#education" class="hover:text-brand-400">Education</a>
          <a href="#contact" class="hover:text-brand-400">Contact</a>
        </nav>
      </div>
    </header>

    <main class="mx-auto max-w-5xl px-4 pb-16 pt-10 md:pt-14">
      <!-- HERO -->
      <section
        id="hero"
        class="mb-10 flex flex-col gap-8 md:mb-16 md:flex-row md:items-center"
      >
        <div class="flex-1 space-y-5">
          <div class="inline-flex items-center gap-2 rounded-full border border-slate-700 bg-slate-900/70 px-3 py-1 text-xs text-slate-300">
            <span class="h-1.5 w-1.5 rounded-full bg-emerald-400"></span>
            <span>Available for remote opportunities</span>
          </div>

          <h1 class="text-3xl font-semibold tracking-tight md:text-4xl">
            Hi, I’m
            <span class="bg-gradient-to-r from-brand-400 to-emerald-400 bg-clip-text text-transparent">
              {{ contacts.name }}
            </span>
          </h1>

          <p class="max-w-xl text-sm leading-relaxed text-slate-300 md:text-base">
            Full Stack Web Developer focused on Vue / Nuxt frontends and Laravel backends,
            with experience in e-commerce, SaaS, and blockchain projects using Web3.js and
            smart contracts.
          </p>

          <div class="flex flex-wrap gap-3">
            <a
              href="#contact"
              class="inline-flex items-center justify-center rounded-xl bg-brand-500 px-4 py-2 text-sm font-medium text-slate-50 shadow-lg shadow-brand-500/40 hover:bg-brand-600"
            >
              Let’s work together
            </a>
            <button
              type="button"
              class="inline-flex items-center justify-center rounded-xl border border-slate-700 bg-slate-900/80 px-4 py-2 text-sm text-slate-200 hover:border-brand-500 hover:text-brand-400"
              @click="showCv = true"
            >
              View CV
            </button>
            <a
              :href="cvUrl"
              target="_blank"
              rel="noopener"
              class="inline-flex items-center justify-center rounded-xl border border-slate-700/80 px-4 py-2 text-sm text-slate-300 hover:border-brand-400"
            >
              Download PDF
            </a>
          </div>

          <div class="flex flex-wrap gap-2 text-xs">
            <div class="chip">
              <span class="chip__label">Location</span>
              <span class="chip__text">Yerevan, Armenia · Remote</span>
            </div>
          </div>
        </div>

        <div class="flex-1">
          <div class="glass-card">
            <h2 class="mb-3 text-sm font-semibold uppercase tracking-wide text-slate-300">
              Contact
            </h2>
            <ul class="space-y-2 text-sm text-slate-300">
              <li>
                <span class="text-slate-400">Phone:</span>
                <span class="ml-2">{{ contacts.phone }}</span>
              </li>
              <li>
                <span class="text-slate-400">Email:</span>
                <a
                  class="ml-2 text-brand-400 hover:underline"
                  :href="`mailto:${contacts.email}`"
                >
                  {{ contacts.email }}
                </a>
              </li>
              <li>
                <span class="text-slate-400">LinkedIn:</span>
                <a
                  class="ml-2 text-brand-400 hover:underline"
                  :href="contacts.linkedin"
                  target="_blank"
                  rel="noopener"
                >
                  linkedin.com
                </a>
              </li>
            </ul>
          </div>
        </div>
      </section>

      <!-- ABOUT -->
      <section id="about" class="mb-12 md:mb-14">
        <div class="glass-card">
          <h2 class="section-title">About</h2>
          <p class="mb-3 text-sm text-slate-300 md:text-base">
            I’m a full stack web developer who enjoys building clean, responsive UIs and
            robust backends. My main tools are Vue / Nuxt on the frontend and Laravel with
            relational databases on the backend.
          </p>
          <p class="text-sm text-slate-300 md:text-base">
            I’ve worked on large-scale e-commerce platforms, complex SaaS dashboards, and
            blockchain-powered applications. I care about maintainable code, good developer
            experience, and clear communication in distributed teams.
          </p>
        </div>
      </section>

      <!-- EXPERIENCE -->
      <section id="experience" class="mb-12 md:mb-14">
        <h2 class="section-title">Experience</h2>
        <div class="space-y-4">
          <article
            v-for="job in experience"
            :key="job.company + job.title"
            class="glass-card"
          >
            <div class="flex flex-col justify-between gap-2 md:flex-row md:items-baseline">
              <div>
                <h3 class="text-base font-semibold md:text-lg">
                  {{ job.title }}
                </h3>
                <p class="text-sm text-brand-300">
                  @ {{ job.company }}
                </p>
              </div>
              <div class="text-xs text-slate-400 md:text-sm">
                <span>{{ job.period }}</span>
              </div>
            </div>
            <ul class="mt-3 list-disc space-y-1 pl-5 text-sm text-slate-300">
              <li v-for="p in job.points" :key="p">
                {{ p }}
              </li>
            </ul>
            <div class="mt-3 flex flex-wrap gap-2">
              <span
                v-for="t in job.tech"
                :key="t"
                class="rounded-full bg-slate-900/80 px-2.5 py-1 text-[11px] text-slate-300"
              >
                {{ t }}
              </span>
            </div>
          </article>
        </div>
      </section>

      <!-- PROJECTS -->
      <section id="projects" class="mb-12 md:mb-14">
        <h2 class="section-title">Highlighted Projects</h2>
        <div class="grid gap-4 md:grid-cols-2">
          <article
            v-for="project in projects"
            :key="project.name"
            class="glass-card flex flex-col"
          >
            <div class="mb-2 flex items-center justify-between gap-3">
              <h3 class="text-base font-semibold md:text-lg">
                {{ project.name }}
              </h3>
              <span class="rounded-full bg-slate-900/80 px-2.5 py-1 text-xs text-slate-400">
                {{ project.type }}
              </span>
            </div>
            <p class="mb-2 text-sm text-slate-300">
              {{ project.description }}
            </p>
            <ul class="mb-3 list-disc space-y-1 pl-5 text-xs text-slate-400 md:text-sm">
              <li v-for="b in project.bullets" :key="b">
                {{ b }}
              </li>
            </ul>
            <div class="mt-auto flex flex-wrap gap-2">
              <span
                v-for="t in project.tech"
                :key="t"
                class="rounded-full bg-slate-900/80 px-2.5 py-1 text-[11px] text-slate-300"
              >
                {{ t }}
              </span>
            </div>
          </article>
        </div>
      </section>

      <!-- SKILLS -->
      <section id="skills" class="mb-12 md:mb-14">
        <h2 class="section-title">Skills</h2>
        <div class="grid gap-4 md:grid-cols-2">
          <article
            v-for="group in skillGroups"
            :key="group.category"
            class="glass-card"
          >
            <h3 class="mb-2 text-sm font-semibold uppercase tracking-wide text-slate-300">
              {{ group.category }}
            </h3>
            <div class="flex flex-wrap gap-2">
              <span
                v-for="skill in group.items"
                :key="skill"
                class="rounded-full bg-slate-900/80 px-2.5 py-1 text-[11px] text-slate-300"
              >
                {{ skill }}
              </span>
            </div>
          </article>
        </div>
      </section>

      <!-- EDUCATION -->
      <section id="education" class="mb-12 md:mb-14">
        <h2 class="section-title">Education</h2>
        <div class="grid gap-4 md:grid-cols-2">
          <article
            v-for="ed in education"
            :key="ed.name"
            class="glass-card"
          >
            <h3 class="text-sm font-semibold md:text-base">
              {{ ed.name }}
            </h3>
            <p class="mt-1 text-xs text-slate-400 md:text-sm">
              {{ ed.detail }}
            </p>
          </article>
        </div>
      </section>

      <!-- CONTACT -->
      <section id="contact">
        <div class="glass-card">
          <h2 class="section-title">Contact</h2>
          <p class="mb-4 text-sm text-slate-300 md:text-base">
            If you’d like to discuss a project, collaboration, or role, feel free to reach out
            by email or phone.
          </p>
          <div class="flex flex-wrap items-center gap-4 text-sm">
            <a
              :href="`mailto:${contacts.email}`"
              class="inline-flex items-center rounded-xl bg-brand-500 px-4 py-2 font-medium text-slate-50 shadow-lg shadow-brand-500/40 hover:bg-brand-600"
            >
              Email me
            </a>
            <span class="text-slate-300">
              or call
              <span class="font-medium">{{ contacts.phone }}</span>
            </span>
          </div>
        </div>
      </section>
    </main>

    <ModalOverlay v-model="showCv" title="Curriculum Vitae">
      <div class="space-y-4">
        <p class="text-sm text-slate-300 md:text-base">
          Interactive preview of my latest CV. Use the buttons below if the inline viewer is blocked by your browser.
        </p>
        <div class="overflow-hidden rounded-xl border border-slate-800 bg-slate-900 shadow-inner">
          <iframe
            :src="cvUrl"
            class="h-[70vh] w-full"
            title="CV PDF preview"
          />
        </div>
        <div class="flex flex-wrap items-center gap-3 text-sm">
          <a
            :href="cvUrl"
            download
            class="inline-flex items-center gap-2 rounded-full bg-brand-500 px-4 py-2 font-medium text-slate-50 shadow-lg shadow-brand-500/30 hover:bg-brand-600"
          >
            Download PDF
          </a>
          <a
            :href="cvUrl"
            target="_blank"
            rel="noopener"
            class="inline-flex items-center gap-2 rounded-full border border-slate-700 px-4 py-2 font-medium text-slate-200 hover:border-brand-400 hover:text-brand-200"
          >
            Open in new tab
          </a>
        </div>
      </div>
    </ModalOverlay>
  </div>
</template>
