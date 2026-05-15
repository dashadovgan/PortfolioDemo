<script setup lang="ts">
import { ref, onMounted } from 'vue'
import TheHeader from '../components/TheHeader.vue'
import TheFooter from '../components/TheFooter.vue'
import BaseButton from '../components/BaseButton.vue'
import GlassCard from '../components/GlassCard.vue'
import TechBadge from '../components/TechBadge.vue'

const projects = [
  {
    title: 'E-commerce Dashboard',
    description: 'A responsive admin panel built with Vue.js and Bootstrap, featuring real-time data visualization.',
    tags: ['Vue.js', 'Bootstrap', 'Chart.js'],
    category: 'Full Stack',
    icon: 'storefront'
  },
  {
    title: 'Fitness Tracker App',
    description: 'A progressive web app for tracking workouts, built with vanilla JavaScript and modern CSS features.',
    tags: ['JavaScript', 'CSS3', 'PWA'],
    category: 'Frontend',
    icon: 'fitness_center'
  },
  {
    title: 'Minimalist Blog Engine',
    description: 'A markdown-based headless CMS geared towards creative writers and technical bloggers.',
    tags: ['TypeScript', 'Node.js', 'Tailwind'],
    category: 'Backend',
    icon: 'edit_note'
  }
]

const skills = [
  { name: 'HTML5', icon: 'html' },
  { name: 'CSS3', icon: 'css' },
  { name: 'JavaScript', icon: 'javascript' },
  { name: 'Vue.js', icon: 'web' },
  { name: 'TypeScript', icon: 'terminal' },
  { name: 'Git', icon: 'commit' },
  { name: 'Tailwind', icon: 'palette' },
  { name: 'Responsive', icon: 'devices' }
]

const experience = [
  {
    role: 'Frontend Developer Intern',
    company: 'TechCorp Inc.',
    period: '2023 - Present',
    description: 'Collaborating with senior developers to build responsive web interfaces using Vue.js and modern CSS frameworks.',
    color: 'primary'
  },
  {
    role: 'Freelance Web Designer',
    company: 'Self-Employed',
    period: '2022 - 2023',
    description: 'Designed and developed custom portfolio and small business websites for local clients.',
    color: 'secondary'
  },
  {
    role: 'Web Development Bootcamp',
    company: 'CodeAcademy',
    period: '2022',
    description: 'Completed an intensive 12-week program focusing on modern JavaScript, HTML5, and CSS3 fundamentals.',
    color: 'tertiary'
  }
]

const isHeroVisible = ref(false)
onMounted(() => {
  setTimeout(() => {
    isHeroVisible.value = true
  }, 100)
})
</script>

<template>
  <div class="min-h-screen">
    <TheHeader />

    <main class="pt-32 px-6 md:px-12 max-w-container-max mx-auto space-y-xl">
      <!-- Hero Section -->
      <section id="hero" class="relative min-h-[70vh] flex items-center justify-center py-20">
        <div class="absolute inset-0 -z-10 bg-mesh opacity-30 rounded-[4rem]"></div>
        
        <div 
          class="text-center max-w-4xl transition-all duration-1000 transform"
          :class="[isHeroVisible ? 'translate-y-0 opacity-100' : 'translate-y-10 opacity-0']"
        >
          <h1 class="text-6xl md:text-8xl font-ubuntu font-bold mb-6 tracking-tight">
            <span class="text-primary block">Alex Chen</span>
            <span class="text-on-background/80">Web Developer</span>
          </h1>
          
          <p class="font-jost text-xl md:text-2xl text-on-surface-variant max-w-2xl mx-auto mb-10 leading-relaxed">
            I craft technical excellence with an emotional soul. Building digital products that feel as good as they function.
          </p>

          <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
            <BaseButton href="#projects">View Projects</BaseButton>
            <BaseButton variant="secondary" href="#about">About Me</BaseButton>
          </div>
        </div>

        <!-- Ambient Orbs -->
        <div class="absolute top-1/4 -right-20 w-80 h-80 bg-primary/10 blur-[100px] rounded-full -z-10 animate-pulse"></div>
        <div class="absolute bottom-1/4 -left-20 w-80 h-80 bg-secondary/10 blur-[100px] rounded-full -z-10 animate-pulse" style="animation-delay: 1s"></div>
      </section>

      <!-- About Section -->
      <section id="about" class="py-xl scroll-mt-32">
        <GlassCard class="grid md:grid-cols-2 gap-12 items-center">
          <div class="relative group">
            <div class="aspect-square rounded-2xl overflow-hidden shadow-2xl relative z-10">
              <img 
                src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=2544&auto=format&fit=crop" 
                alt="Portrait of Alex Chen"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
              >
              <div class="absolute inset-0 bg-primary/20 mix-blend-overlay"></div>
            </div>
            <!-- Decorative corner -->
            <div class="absolute -top-4 -left-4 w-24 h-24 border-t-4 border-l-4 border-primary rounded-tl-3xl -z-0"></div>
          </div>

          <div class="space-y-6">
            <h2 class="text-4xl font-ubuntu font-bold text-primary">Emotional Technicality</h2>
            <p class="text-lg leading-relaxed text-on-surface-variant">
              Since 2022, I've been on a mission to prove that code isn't just about logic—it's about connection. My journey started with a deep curiosity for how visual elements influence our daily digital emotions.
            </p>
            <p class="text-lg leading-relaxed text-on-surface-variant">
              Today, I focus on creating high-fidelity interfaces that breathe. Using glassmorphic depth and soft minimalism, I build experiences that feel familiar yet futuristic.
            </p>
            <div class="pt-4">
              <BaseButton variant="tertiary" href="#contact" class="group">
                Work together 
                <span class="material-symbols-outlined ml-2 transition-transform group-hover:translate-x-2">arrow_forward</span>
              </BaseButton>
            </div>
          </div>
        </GlassCard>
      </section>

      <!-- Skills Section -->
      <section id="skills" class="py-xl scroll-mt-32 text-center">
        <h2 class="text-4xl md:text-5xl font-ubuntu font-bold mb-16 underline decoration-primary/20 underline-offset-8">Technical Palette</h2>
        
        <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-6">
          <div 
            v-for="skill in skills" 
            :key="skill.name"
            class="group bg-white/40 backdrop-blur-md p-8 rounded-2xl border border-white/40 hover:bg-white/80 transition-all duration-300 hover:-translate-y-2 hover:shadow-xl"
          >
            <span class="material-symbols-outlined text-4xl text-primary mb-4 block group-hover:scale-125 transition-transform">{{ skill.icon }}</span>
            <span class="font-label-md text-on-surface">{{ skill.name }}</span>
          </div>
        </div>
      </section>

      <!-- Projects Section -->
      <section id="projects" class="py-xl scroll-mt-32">
        <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-6">
          <div class="max-w-xl">
            <h2 class="text-5xl font-ubuntu font-bold mb-4">Selected Works</h2>
            <p class="text-lg text-on-surface-variant">A curated collection of projects where code meets artistry.</p>
          </div>
          <BaseButton variant="secondary" href="https://github.com/alexchen">View Github</BaseButton>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <GlassCard 
            v-for="project in projects" 
            :key="project.title" 
            hoverable
            class="flex flex-col justify-between group"
          >
            <div>
              <div class="h-48 rounded-xl bg-surface-container-highest mb-6 flex items-center justify-center relative overflow-hidden">
                <span class="material-symbols-outlined text-6xl text-primary/30">{{ project.icon }}</span>
                <div class="absolute inset-0 bg-gradient-to-tr from-primary/10 to-transparent opacity-0 group-hover:opacity-100 transition-opacity"></div>
              </div>
              <div class="space-y-3">
                <span class="text-xs font-label-md text-primary tracking-widest uppercase">{{ project.category }}</span>
                <h3 class="text-2xl font-ubuntu font-bold">{{ project.title }}</h3>
                <p class="text-on-surface-variant line-clamp-3">{{ project.description }}</p>
              </div>
            </div>
            
            <div class="mt-8 flex flex-wrap gap-2">
              <TechBadge v-for="tag in project.tags" :key="tag" :label="tag" />
            </div>
          </GlassCard>
        </div>
      </section>

      <!-- Experience Journey -->
      <section id="experience" class="py-xl scroll-mt-32">
        <h2 class="text-4xl font-ubuntu font-bold text-center mb-16">Learning Journey</h2>
        
        <div class="max-w-3xl mx-auto space-y-12 relative">
          <!-- Timeline line -->
          <div class="absolute left-0 md:left-1/2 top-4 bottom-4 w-1 bg-gradient-to-b from-primary via-secondary to-tertiary opacity-10 -translate-x-1/2"></div>
          
          <div 
            v-for="(job, index) in experience" 
            :key="job.company"
            class="relative flex flex-col md:flex-row gap-8 items-start md:items-center"
            :class="index % 2 === 0 ? 'md:flex-row-reverse' : ''"
          >
            <!-- Timeline dot -->
            <div 
              class="absolute left-0 md:left-1/2 top-4 w-4 h-4 rounded-full border-4 border-background -translate-x-1/2 z-10"
              :class="`bg-${job.color}`"
            ></div>

            <div class="w-full md:w-[calc(50%-2rem)]">
              <GlassCard 
                class="hover:shadow-lg transition-shadow"
                :class="`border-l-4 border-${job.color}/40`"
              >
                <span class="text-xs font-label-md opacity-60 mb-1 block">{{ job.period }}</span>
                <h3 class="text-xl font-ubuntu font-bold mb-1">{{ job.role }}</h3>
                <p class="font-bold text-primary mb-4">{{ job.company }}</p>
                <p class="text-sm leading-relaxed text-on-surface-variant">{{ job.description }}</p>
              </GlassCard>
            </div>
          </div>
        </div>
      </section>

      <!-- Contact Section -->
      <section id="contact" class="py-xl pb-20 scroll-mt-32">
        <div class="bg-primary/5 rounded-[3rem] p-12 md:p-20 text-center relative overflow-hidden backdrop-blur-sm border border-primary/10">
          <div class="absolute top-0 right-0 p-8 opacity-10">
            <span class="material-symbols-outlined text-9xl">chat_bubble</span>
          </div>
          
          <h2 class="text-5xl md:text-7xl font-ubuntu font-bold mb-8">Let's create something <br><span class="text-primary italic">extraordinary.</span></h2>
          <p class="text-xl text-on-surface-variant mb-12 max-w-2xl mx-auto">
            Ready to mix high-fidelity tech with a personal touch? My digital door is always open for bold ideas.
          </p>
          
          <div class="flex flex-col sm:flex-row gap-6 justify-center items-center">
            <BaseButton href="mailto:alex@luminous.dev" class="w-full sm:w-auto">Start a Conversation</BaseButton>
            <div class="flex gap-4">
              <a href="#" class="w-12 h-12 glass rounded-full flex items-center justify-center hover:bg-primary hover:text-white transition-all duration-300">
                <span class="material-symbols-outlined">alternate_email</span>
              </a>
              <a href="#" class="w-12 h-12 glass rounded-full flex items-center justify-center hover:bg-primary hover:text-white transition-all duration-300">
                <span class="material-symbols-outlined">link</span>
              </a>
            </div>
          </div>
        </div>
      </section>
    </main>

    <TheFooter />
  </div>
</template>

<style scoped>
.bg-mesh {
  background-image: 
    radial-gradient(at 100% 0%, rgba(114, 20, 255, 0.1) 0px, transparent 50%),
    radial-gradient(at 0% 100%, rgba(134, 77, 255, 0.1) 0px, transparent 50%);
}

#hero h1 {
  line-height: 0.95;
}
</style>
