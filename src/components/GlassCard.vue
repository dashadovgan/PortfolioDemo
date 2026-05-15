<script setup lang="ts">
interface Props {
  hoverable?: boolean
  id?: string
}

defineProps<Props>()
</script>

<template>
  <div 
    :id="id"
    class="glass rounded-xl p-8 transition-all duration-500 overflow-hidden"
    :class="{ 'hover:scale-[1.02] hover:shadow-xl cursor-default': hoverable }"
  >
    <slot />
  </div>
</template>
