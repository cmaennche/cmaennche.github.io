<template>
  <main class="min-h-screen bg-slate-950 text-slate-100">
    <section class="mx-auto flex max-w-6xl flex-col gap-12 px-6 py-20">
      <!-- Hero -->
      <div class="grid gap-8 lg:grid-cols-[1.3fr_0.7fr] lg:items-center">
        <div>
          <p class="mb-4 text-sm font-medium uppercase tracking-[0.3em] text-cyan-400">
            Portfolio / Resume
          </p>

          <h1 class="text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl">
            Chris Maennche
          </h1>

          <p class="mt-4 max-w-2xl text-lg leading-8 text-slate-300">
            Full-stack developer focused on practical web applications, thoughtful UX, and reliable implementation.
            I build with modern JavaScript frameworks, backend tooling, and a healthy respect for things that should
            have been documented better the first time.
          </p>

          <div class="mt-8 flex flex-wrap gap-4">
            <a
                href="#projects"
                class="rounded-xl bg-cyan-400 px-5 py-3 font-medium text-slate-950 transition hover:bg-cyan-300"
            >
              View Projects
            </a>
            <a
                href="#contact"
                class="rounded-xl border border-slate-700 px-5 py-3 font-medium text-slate-100 transition hover:bg-slate-900"
            >
              Contact Me
            </a>
          </div>
        </div>

        <div class="rounded-3xl border border-slate-800 bg-slate-900 p-6 shadow-2xl shadow-cyan-950/20">
          <h2 class="text-xl font-semibold">Quick Info</h2>
          <dl class="mt-6 space-y-4 text-sm">
            <div>
              <dt class="text-slate-400">Role</dt>
              <dd class="mt-1 text-slate-100">Developer</dd>
            </div>
            <div>
              <dt class="text-slate-400">Location</dt>
              <dd class="mt-1 text-slate-100">Oklahoma, USA</dd>
            </div>
            <div>
              <dt class="text-slate-400">Focus</dt>
              <dd class="mt-1 text-slate-100">Web apps, portals, and product development</dd>
            </div>
            <div>
              <dt class="text-slate-400">GitHub</dt>
              <dd class="mt-1 text-slate-100">
                <a
                    href="https://github.com/cmaennche"
                    target="_blank"
                    rel="noreferrer"
                    class="text-cyan-400 hover:underline"
                >
                  github.com/cmaennche
                </a>
              </dd>
            </div>
          </dl>
        </div>
      </div>

      <!-- About -->
      <section class="grid gap-6 lg:grid-cols-2">
        <div class="rounded-3xl border border-slate-800 bg-slate-900 p-8">
          <h2 class="text-2xl font-semibold">About</h2>
          <p class="mt-4 leading-7 text-slate-300">
            I design and build software that solves real problems. My work spans frontend interfaces, backend logic,
            and full-stack application development. I care about clarity, performance, and shipping things that work
            without drama. A bold strategy, obviously.
          </p>
        </div>

        <div class="rounded-3xl border border-slate-800 bg-slate-900 p-8">
          <h2 class="text-2xl font-semibold">Skills</h2>
          <div class="mt-4 flex flex-wrap gap-3">
            <span
                v-for="skill in skills"
                :key="skill"
                class="rounded-full border border-slate-700 bg-slate-950 px-4 py-2 text-sm text-slate-200"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section id="projects" class="space-y-6">
        <div>
          <p class="text-sm uppercase tracking-[0.3em] text-cyan-400">Projects</p>
          <h2 class="mt-2 text-3xl font-semibold">Featured Work</h2>
        </div>

        <div class="grid gap-6 md:grid-cols-2">
          <article
              v-for="project in projects"
              :key="project.name"
              class="rounded-3xl border border-slate-800 bg-slate-900 p-8 transition hover:-translate-y-1 hover:border-cyan-500/40"
          >
            <div class="flex items-start justify-between gap-4">
              <div>
                <h3 class="text-xl font-semibold">{{ project.name }}</h3>
                <p class="mt-2 leading-7 text-slate-300">{{ project.description }}</p>
              </div>
              <span class="rounded-full bg-cyan-400/10 px-3 py-1 text-xs font-medium text-cyan-300">
                Featured
              </span>
            </div>

            <div class="mt-6 flex flex-wrap gap-2">
              <span
                  v-for="tech in project.tech"
                  :key="tech"
                  class="rounded-full bg-slate-950 px-3 py-1 text-xs text-slate-300"
              >
                {{ tech }}
              </span>
            </div>

            <div class="mt-6">
              <a
                  :href="project.link"
                  target="_blank"
                  rel="noreferrer"
                  class="text-cyan-400 hover:underline"
              >
                View Project →
              </a>
            </div>
          </article>
        </div>
      </section>

      <!-- Experience -->
      <section class="rounded-3xl border border-slate-800 bg-slate-900 p-8">
        <h2 class="text-2xl font-semibold">Experience</h2>
        <div class="mt-6 space-y-6">
          <div class="border-l border-slate-700 pl-4">
            <h3 class="text-lg font-medium">Studio.Maennche.com</h3>
            <p class="mt-1 text-slate-300">
              Worked on the Studio.Maennche.com platform, contributing to the development and refinement of the
              product experience.
            </p>
          </div>

          <div class="border-l border-slate-700 pl-4">
            <h3 class="text-lg font-medium">portal.crowdchow.app</h3>
            <p class="mt-1 text-slate-300">
              Built portal.crowdchow.app, developing the customer-facing portal and supporting the core experience.
            </p>
          </div>
        </div>
      </section>

      <!-- Contact -->
      <section id="contact" class="rounded-3xl border border-slate-800 bg-slate-900 p-8">
        <h2 class="text-2xl font-semibold">Contact</h2>
        <p class="mt-4 max-w-2xl leading-7 text-slate-300">
          If you'd like to talk about web development, product work, or a project that needs to be built without
          unnecessary ceremony, feel free to reach out.
        </p>

        <div class="mt-6 flex flex-wrap gap-4">
          <a
              href="https://github.com/cmaennche"
              target="_blank"
              rel="noreferrer"
              class="rounded-xl bg-cyan-400 px-5 py-3 font-medium text-slate-950 transition hover:bg-cyan-300"
          >
            GitHub Profile
          </a>
          <a
              href="mailto:christopher@maennche.com"
              class="rounded-xl border border-slate-700 px-5 py-3 font-medium text-slate-100 transition hover:bg-slate-950"
          >
            Email Me
          </a>
        </div>
      </section>
    </section>
  </main>
</template>

<script setup lang="ts">
const skills = [
  'JavaScript',
  'TypeScript',
  'Vue',
  'Nuxt',
  'HTML',
  'CSS',
  'Node.js',
  'API Integration',
  'UI Development',
  'Full-Stack Development',
]

const projects = [
  {
    name: 'Studio.Maennche.com',
    description:
        'A platform I worked on to support product and workflow needs with a polished user experience.',
    tech: ['Nuxt', 'Vue', 'TypeScript', 'UI/UX'],
    link: 'https://studio.maennche.com',
  },
  {
    name: 'portal.crowdchow.app',
    description:
        'A customer portal I built with a focus on usability, structure, and practical functionality.',
    tech: ['Vue', 'Nuxt', 'Frontend', 'Portal'],
    link: 'https://portal.crowdchow.app',
  },
]
</script>