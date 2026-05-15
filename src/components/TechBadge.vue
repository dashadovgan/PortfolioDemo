<script setup lang="ts">
interface Props {
  label: string
  id?: string
}
defineProps<Props>()
</script>

<template>
  <span 
    :id="id"
    class="inline-flex items-center px-4 py-1.5 rounded-full bg-secondary-container text-on-secondary-container font-label-md tracking-wider text-xs"
  >
    {{ label }}
  </span>
</template>
