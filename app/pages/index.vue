<template>
  <main class="relative min-h-screen overflow-hidden bg-[#070b14] text-slate-100">
    <!-- Background: layered radial color fields + grid + grain, so blur/saturate has something to work with -->
    <div class="pointer-events-none fixed inset-0 -z-10">
      <div
          class="absolute inset-0 bg-cover bg-center"
          style="background-image: url(/background.png);"
      ></div>
      <div
          class="absolute inset-0 opacity-[0.06]"
          style="background-image: linear-gradient(to right, #fff 1px, transparent 1px), linear-gradient(to bottom, #fff 1px, transparent 1px); background-size: 48px 48px;"
      ></div>
      <div
          class="absolute inset-0 opacity-[0.4] mix-blend-overlay"
          :style="{ backgroundImage: `url(${noiseDataUrl})` }"
      ></div>
      <div class="absolute inset-0 bg-gradient-to-b from-transparent via-transparent to-[#070b14]"></div>
    </div>

    <section class="relative mx-auto flex max-w-6xl flex-col gap-10 px-6 py-20">
      <!-- Hero -->
      <div class="grid gap-6 lg:grid-cols-[1.3fr_0.7fr] lg:items-center">
        <div class="glass glass-lg p-10">
          <p class="mb-4 text-sm font-medium uppercase tracking-[0.3em] text-cyan-200">
            Portfolio / Resume
          </p>

          <h1 class="text-4xl font-bold tracking-tight text-white sm:text-5xl lg:text-6xl">
            Chris Maennche
          </h1>

          <p class="mt-4 max-w-2xl text-lg leading-8 text-slate-200/85">
            Full-stack developer focused on practical web applications, thoughtful UX, and reliable implementation.
            I build with modern JavaScript frameworks, backend tooling, and a healthy respect for things that should
            have been documented better the first time.
          </p>

          <div class="mt-8 flex flex-wrap gap-4">
            <a href="#projects" class="glass-btn glass-btn-solid">View Projects</a>
            <a href="#contact" class="glass-btn glass-btn-outline">Contact Me</a>
          </div>
        </div>

        <div class="glass glass-lg p-6">
          <h2 class="text-xl font-semibold text-white">Quick Info</h2>
          <dl class="mt-6 space-y-3 text-sm">
            <div class="glass-chip">
              <dt class="text-slate-300/70">Role</dt>
              <dd class="mt-1 text-slate-100">Developer</dd>
            </div>
            <div class="glass-chip">
              <dt class="text-slate-300/70">Location</dt>
              <dd class="mt-1 text-slate-100">Oklahoma, USA</dd>
            </div>
            <div class="glass-chip">
              <dt class="text-slate-300/70">Focus</dt>
              <dd class="mt-1 text-slate-100">Web apps, portals, and product development</dd>
            </div>
            <div class="glass-chip">
              <dt class="text-slate-300/70">GitHub</dt>
              <dd class="mt-1 text-slate-100">
                <a href="https://github.com/cmaennche" target="_blank" rel="noreferrer" class="text-cyan-300 hover:underline">
                  github.com/cmaennche
                </a>
              </dd>
            </div>
          </dl>
        </div>
      </div>

      <!-- About -->
      <section class="grid gap-6 lg:grid-cols-2">
        <div class="glass p-8">
          <h2 class="text-2xl font-semibold text-white">About</h2>
          <p class="mt-4 leading-7 text-slate-200/85">
            I design and build software that solves real problems. My work spans frontend interfaces, backend logic,
            and full-stack application development. I care about clarity, performance, and shipping things that work
            without drama. A bold strategy, obviously.
          </p>
        </div>

        <div class="glass p-8">
          <h2 class="text-2xl font-semibold text-white">Skills</h2>
          <div class="mt-4 flex flex-wrap gap-3">
            <span v-for="skill in skills" :key="skill" class="glass-pill">{{ skill }}</span>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section id="projects" class="space-y-6">
        <div>
          <p class="text-sm uppercase tracking-[0.3em] text-cyan-200">Projects</p>
          <h2 class="mt-2 text-3xl font-semibold text-white">Featured Work</h2>
        </div>

        <div class="grid gap-6 md:grid-cols-2">
          <article v-for="project in projects" :key="project.name" class="glass glass-hover p-8">
            <div class="flex items-start justify-between gap-4">
              <div>
                <h3 class="text-xl font-semibold text-white">{{ project.name }}</h3>
                <p class="mt-2 leading-7 text-slate-200/85">{{ project.description }}</p>
              </div>
              <span class="glass-tag">Featured</span>
            </div>

            <div class="mt-6 flex flex-wrap gap-2">
              <span v-for="tech in project.tech" :key="tech" class="glass-pill glass-pill-sm">{{ tech }}</span>
            </div>

            <div class="mt-6">
              <a :href="project.link" target="_blank" rel="noreferrer" class="text-cyan-300 hover:underline">
                View Project →
              </a>
            </div>
          </article>
        </div>
      </section>

      <!-- Experience -->
      <section class="glass p-8">
        <h2 class="text-2xl font-semibold text-white">Experience</h2>
        <div class="mt-6 space-y-4">
          <div class="glass-chip glass-chip-lg">
            <h3 class="text-lg font-medium text-white">Studio.Maennche.com</h3>
            <p class="mt-1 text-slate-200/85">
              Worked on the Studio.Maennche.com platform, contributing to the development and refinement of the
              product experience.
            </p>
          </div>

          <div class="glass-chip glass-chip-lg">
            <h3 class="text-lg font-medium text-white">portal.crowdchow.app</h3>
            <p class="mt-1 text-slate-200/85">
              Built portal.crowdchow.app, developing the customer-facing portal and supporting the core experience.
            </p>
          </div>
        </div>
      </section>

      <!-- Contact -->
      <section id="contact" class="glass glass-lg p-8">
        <h2 class="text-2xl font-semibold text-white">Contact</h2>
        <p class="mt-4 max-w-2xl leading-7 text-slate-200/85">
          If you'd like to talk about web development, product work, or a project that needs to be built without
          unnecessary ceremony, feel free to reach out.
        </p>

        <div class="mt-6 flex flex-wrap gap-4">
          <a href="https://github.com/cmaennche" target="_blank" rel="noreferrer" class="glass-btn glass-btn-solid">
            GitHub Profile
          </a>
          <a href="mailto:christopher@maennche.com" class="glass-btn glass-btn-outline">Email Me</a>
        </div>
      </section>
    </section>
  </main>
</template>

<script setup lang="ts">
const noiseSvg = `<svg xmlns="http://www.w3.org/2000/svg" width="120" height="120"><filter id="n"><feTurbulence type="fractalNoise" baseFrequency="0.9" numOctaves="2" stitchTiles="stitch"/></filter><rect width="100%" height="100%" filter="url(#n)" opacity="0.5"/></svg>`
const noiseDataUrl = `data:image/svg+xml,${encodeURIComponent(noiseSvg)}`

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

<style scoped>
/* Core glass surface: blur + saturate the backdrop, faint fill, gradient border,
   and a soft inset highlight along the top edge to fake a specular reflection. */
.glass {
  position: relative;
  border-radius: 1.75rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.09), rgba(255, 255, 255, 0.03));
  backdrop-filter: blur(24px) saturate(180%);
  -webkit-backdrop-filter: blur(24px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.14);
  box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.25),
      inset 0 0 40px rgba(255, 255, 255, 0.03),
      0 20px 50px rgba(0, 0, 0, 0.45);
  transition: background 0.3s ease, border-color 0.3s ease, transform 0.3s ease;
}

.glass-lg {
  backdrop-filter: blur(32px) saturate(200%);
  -webkit-backdrop-filter: blur(32px) saturate(200%);
}

.glass-hover:hover {
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.13), rgba(255, 255, 255, 0.05));
  border-color: rgba(56, 214, 255, 0.35);
  transform: translateY(-4px);
}

/* Nested glass chips: slightly darker/more opaque than parent so depth reads clearly */
.glass-chip {
  border-radius: 1rem;
  padding: 0.75rem 1rem;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(14px) saturate(160%);
  -webkit-backdrop-filter: blur(14px) saturate(160%);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.15);
}

.glass-chip-lg {
  padding: 1.25rem 1.5rem;
}

.glass-pill {
  border-radius: 999px;
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
  color: rgba(241, 245, 249, 0.92);
  background: rgba(255, 255, 255, 0.07);
  backdrop-filter: blur(12px) saturate(160%);
  -webkit-backdrop-filter: blur(12px) saturate(160%);
  border: 1px solid rgba(255, 255, 255, 0.12);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.18);
  transition: background 0.2s ease;
}
.glass-pill:hover {
  background: rgba(255, 255, 255, 0.12);
}
.glass-pill-sm {
  padding: 0.3rem 0.7rem;
  font-size: 0.75rem;
}

.glass-tag {
  border-radius: 999px;
  padding: 0.3rem 0.8rem;
  font-size: 0.75rem;
  font-weight: 500;
  color: #a5f3ff;
  background: rgba(56, 214, 255, 0.14);
  border: 1px solid rgba(56, 214, 255, 0.3);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
}

/* Buttons: solid = bright frosted white glass, outline = translucent dark glass */
.glass-btn {
  border-radius: 999px;
  padding: 0.75rem 1.5rem;
  font-weight: 500;
  backdrop-filter: blur(18px) saturate(180%);
  -webkit-backdrop-filter: blur(18px) saturate(180%);
  transition: transform 0.2s ease, background 0.2s ease;
  display: inline-block;
}
.glass-btn:hover {
  transform: translateY(-2px);
}
.glass-btn-solid {
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.98), rgba(255, 255, 255, 0.85));
  color: #0a1220;
  border: 1px solid rgba(255, 255, 255, 0.6);
  box-shadow: 0 8px 24px rgba(56, 214, 255, 0.25), inset 0 1px 0 rgba(255, 255, 255, 0.9);
}
.glass-btn-outline {
  background: rgba(255, 255, 255, 0.06);
  color: #f1f5f9;
  border: 1px solid rgba(255, 255, 255, 0.18);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2);
}
.glass-btn-outline:hover {
  background: rgba(255, 255, 255, 0.12);
}
</style>