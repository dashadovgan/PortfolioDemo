<template>
  <footer class="bg-inverse-surface text-inverse-on-surface w-full rounded-t-[40px] mt-xl py-12 px-6 md:px-12">
    <div class="max-w-container-max mx-auto flex flex-col md:flex-row justify-between items-center gap-8">
      <div>
        <h3 class="font-ubuntu font-bold text-2xl mb-2">Luminous Portfolio</h3>
        <p class="font-jost opacity-60 text-sm">Crafting high-fidelity digital experiences.</p>
      </div>

      <div class="flex gap-4">
        <a v-for="item in ['LinkedIn', 'GitHub', 'Twitter', 'Dribbble']" 
           :key="item" 
           href="#" 
           class="text-sm font-medium hover:text-primary-fixed-dim transition-colors"
        >
          {{ item }}
        </a>
      </div>

      <p class="text-xs opacity-40">
        &copy; 2024 Alex Chen. All rights reserved.
      </p>
    </div>
  </footer>
</template>
