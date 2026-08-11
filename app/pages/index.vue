<template>
  <main class="relative min-h-screen overflow-hidden bg-gradient-to-br from-[#0b1120] via-[#0e1a2e] to-[#0a1220] text-slate-100">
    <!-- Ambient background: grid texture + saturated color blobs so the glass blur reads clearly -->
    <div class="pointer-events-none fixed inset-0 -z-10">
      <div
          class="absolute inset-0 opacity-[0.07]"
          style="background-image: linear-gradient(to right, #ffffff 1px, transparent 1px), linear-gradient(to bottom, #ffffff 1px, transparent 1px); background-size: 56px 56px;"
      ></div>
      <div class="absolute -top-32 left-[8%] h-[34rem] w-[34rem] rounded-full bg-cyan-400/40 blur-[110px]"></div>
      <div class="absolute top-1/4 right-[5%] h-[30rem] w-[30rem] rounded-full bg-fuchsia-500/35 blur-[120px]"></div>
      <div class="absolute top-[55%] left-[35%] h-[26rem] w-[26rem] rounded-full bg-violet-500/30 blur-[110px]"></div>
      <div class="absolute bottom-[-6rem] right-[15%] h-[30rem] w-[30rem] rounded-full bg-emerald-400/25 blur-[130px]"></div>
      <div class="absolute inset-0 bg-gradient-to-b from-transparent via-transparent to-[#0a1220]/60"></div>
    </div>

    <section class="mx-auto flex max-w-6xl flex-col gap-10 px-6 py-20">
      <!-- Hero -->
      <div class="grid gap-6 lg:grid-cols-[1.3fr_0.7fr] lg:items-center">
        <div
            class="rounded-[2rem] border border-white/10 bg-white/[0.04] p-10 shadow-[0_8px_32px_rgba(0,0,0,0.4)] backdrop-blur-2xl"
        >
          <p class="mb-4 text-sm font-medium uppercase tracking-[0.3em] text-cyan-300/90">
            Portfolio / Resume
          </p>

          <h1 class="text-4xl font-bold tracking-tight text-white drop-shadow-sm sm:text-5xl lg:text-6xl">
            Chris Maennche
          </h1>

          <p class="mt-4 max-w-2xl text-lg leading-8 text-slate-300/90">
            Full-stack developer focused on practical web applications, thoughtful UX, and reliable implementation.
            I build with modern JavaScript frameworks, backend tooling, and a healthy respect for things that should
            have been documented better the first time.
          </p>

          <div class="mt-8 flex flex-wrap gap-4">
            <a
                href="#projects"
                class="rounded-full border border-white/20 bg-white/90 px-6 py-3 font-medium text-slate-900 shadow-lg shadow-cyan-500/20 backdrop-blur-xl transition hover:bg-white"
            >
              View Projects
            </a>
            <a
                href="#contact"
                class="rounded-full border border-white/15 bg-white/[0.06] px-6 py-3 font-medium text-slate-100 backdrop-blur-xl transition hover:bg-white/[0.12]"
            >
              Contact Me
            </a>
          </div>
        </div>

        <div
            class="rounded-[2rem] border border-white/10 bg-white/[0.06] p-6 shadow-[0_8px_32px_rgba(0,0,0,0.4)] backdrop-blur-2xl"
        >
          <h2 class="text-xl font-semibold text-white">Quick Info</h2>
          <dl class="mt-6 space-y-4 text-sm">
            <div class="rounded-2xl border border-white/10 bg-white/[0.04] p-3 backdrop-blur-xl">
              <dt class="text-slate-400">Role</dt>
              <dd class="mt-1 text-slate-100">Developer</dd>
            </div>
            <div class="rounded-2xl border border-white/10 bg-white/[0.04] p-3 backdrop-blur-xl">
              <dt class="text-slate-400">Location</dt>
              <dd class="mt-1 text-slate-100">Oklahoma, USA</dd>
            </div>
            <div class="rounded-2xl border border-white/10 bg-white/[0.04] p-3 backdrop-blur-xl">
              <dt class="text-slate-400">Focus</dt>
              <dd class="mt-1 text-slate-100">Web apps, portals, and product development</dd>
            </div>
            <div class="rounded-2xl border border-white/10 bg-white/[0.04] p-3 backdrop-blur-xl">
              <dt class="text-slate-400">GitHub</dt>
              <dd class="mt-1 text-slate-100">
                <a
                    href="https://github.com/cmaennche"
                    target="_blank"
                    rel="noreferrer"
                    class="text-cyan-300 hover:underline"
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
        <div
            class="rounded-[2rem] border border-white/10 bg-white/[0.05] p-8 shadow-[0_8px_32px_rgba(0,0,0,0.35)] backdrop-blur-2xl transition hover:bg-white/[0.07]"
        >
          <h2 class="text-2xl font-semibold text-white">About</h2>
          <p class="mt-4 leading-7 text-slate-300/90">
            I design and build software that solves real problems. My work spans frontend interfaces, backend logic,
            and full-stack application development. I care about clarity, performance, and shipping things that work
            without drama. A bold strategy, obviously.
          </p>
        </div>

        <div
            class="rounded-[2rem] border border-white/10 bg-white/[0.05] p-8 shadow-[0_8px_32px_rgba(0,0,0,0.35)] backdrop-blur-2xl transition hover:bg-white/[0.07]"
        >
          <h2 class="text-2xl font-semibold text-white">Skills</h2>
          <div class="mt-4 flex flex-wrap gap-3">
            <span
                v-for="skill in skills"
                :key="skill"
                class="rounded-full border border-white/15 bg-white/[0.08] px-4 py-2 text-sm text-slate-100 backdrop-blur-xl transition hover:bg-white/[0.14]"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section id="projects" class="space-y-6">
        <div>
          <p class="text-sm uppercase tracking-[0.3em] text-cyan-300/90">Projects</p>
          <h2 class="mt-2 text-3xl font-semibold text-white">Featured Work</h2>
        </div>

        <div class="grid gap-6 md:grid-cols-2">
          <article
              v-for="project in projects"
              :key="project.name"
              class="rounded-[2rem] border border-white/10 bg-white/[0.05] p-8 shadow-[0_8px_32px_rgba(0,0,0,0.35)] backdrop-blur-2xl transition hover:-translate-y-1 hover:border-cyan-400/30 hover:bg-white/[0.08]"
          >
            <div class="flex items-start justify-between gap-4">
              <div>
                <h3 class="text-xl font-semibold text-white">{{ project.name }}</h3>
                <p class="mt-2 leading-7 text-slate-300/90">{{ project.description }}</p>
              </div>
              <span
                  class="rounded-full border border-cyan-300/20 bg-cyan-400/10 px-3 py-1 text-xs font-medium text-cyan-200 backdrop-blur-xl"
              >
                Featured
              </span>
            </div>

            <div class="mt-6 flex flex-wrap gap-2">
              <span
                  v-for="tech in project.tech"
                  :key="tech"
                  class="rounded-full border border-white/10 bg-white/[0.06] px-3 py-1 text-xs text-slate-200 backdrop-blur-xl"
              >
                {{ tech }}
              </span>
            </div>

            <div class="mt-6">
              <a
                  :href="project.link"
                  target="_blank"
                  rel="noreferrer"
                  class="text-cyan-300 hover:underline"
              >
                View Project →
              </a>
            </div>
          </article>
        </div>
      </section>

      <!-- Experience -->
      <section
          class="rounded-[2rem] border border-white/10 bg-white/[0.05] p-8 shadow-[0_8px_32px_rgba(0,0,0,0.35)] backdrop-blur-2xl"
      >
        <h2 class="text-2xl font-semibold text-white">Experience</h2>
        <div class="mt-6 space-y-6">
          <div class="rounded-2xl border border-white/10 bg-white/[0.04] p-5 backdrop-blur-xl">
            <h3 class="text-lg font-medium text-white">Studio.Maennche.com</h3>
            <p class="mt-1 text-slate-300/90">
              Worked on the Studio.Maennche.com platform, contributing to the development and refinement of the
              product experience.
            </p>
          </div>

          <div class="rounded-2xl border border-white/10 bg-white/[0.04] p-5 backdrop-blur-xl">
            <h3 class="text-lg font-medium text-white">portal.crowdchow.app</h3>
            <p class="mt-1 text-slate-300/90">
              Built portal.crowdchow.app, developing the customer-facing portal and supporting the core experience.
            </p>
          </div>
        </div>
      </section>

      <!-- Contact -->
      <section
          id="contact"
          class="rounded-[2rem] border border-white/10 bg-white/[0.05] p-8 shadow-[0_8px_32px_rgba(0,0,0,0.35)] backdrop-blur-2xl"
      >
        <h2 class="text-2xl font-semibold text-white">Contact</h2>
        <p class="mt-4 max-w-2xl leading-7 text-slate-300/90">
          If you'd like to talk about web development, product work, or a project that needs to be built without
          unnecessary ceremony, feel free to reach out.
        </p>

        <div class="mt-6 flex flex-wrap gap-4">
          <a
              href="https://github.com/cmaennche"
              target="_blank"
              rel="noreferrer"
              class="rounded-full border border-white/20 bg-white/90 px-6 py-3 font-medium text-slate-900 shadow-lg shadow-cyan-500/20 backdrop-blur-xl transition hover:bg-white"
          >
            GitHub Profile
          </a>
          <a
              href="mailto:christopher@maennche.com"
              class="rounded-full border border-white/15 bg-white/[0.06] px-6 py-3 font-medium text-slate-100 backdrop-blur-xl transition hover:bg-white/[0.12]"
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