<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const navLinks = [
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Projects', href: '#projects' },
  { name: 'Contact', href: '#contact' },
]
</script>

<template>
  <header 
    class="fixed top-6 left-1/2 -translate-x-1/2 w-[90%] max-w-4xl z-50 transition-all duration-300"
    :class="{ 'top-2': isScrolled }"
  >
    <nav class="glass rounded-full px-6 md:px-8 py-3 flex items-center justify-between shadow-lg">
      <div class="flex items-center gap-2">
        <div class="w-8 h-8 bg-primary rounded-lg flex items-center justify-center text-white">
          <span class="material-symbols-outlined text-sm">code</span>
        </div>
        <span class="font-ubuntu font-bold text-lg hidden sm:block">Luminous</span>
      </div>

      <ul class="flex items-center gap-6 md:gap-8">
        <li v-for="link in navLinks" :key="link.name">
          <a 
            :href="link.href" 
            class="font-jost text-sm font-medium text-on-surface-variant hover:text-primary transition-colors relative group"
          >
            {{ link.name }}
            <span class="absolute -bottom-1 left-1/2 -translate-x-1/2 w-1 h-1 bg-primary rounded-full opacity-0 group-hover:opacity-100 transition-opacity"></span>
          </a>
        </li>
      </ul>

      <div class="hidden md:block">
        <a href="#contact" class="bg-primary text-on-primary px-5 py-2 rounded-full font-label-md text-xs hover:ambient-shadow transition-all">
          Hire Me
        </a>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.glass {
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(24px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}
</style>
