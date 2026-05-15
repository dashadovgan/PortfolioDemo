<script setup lang="ts">
import { computed } from 'vue'

interface Props {
  variant?: 'primary' | 'secondary' | 'tertiary'
  href?: string
  id?: string
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary'
})

const baseClass = "inline-flex items-center justify-center font-label-md transition-all duration-300 disabled:opacity-50 disabled:pointer-events-none active:scale-95"

const variantClasses = {
  primary: "bg-primary text-on-primary px-8 py-4 rounded-lg shadow-lg hover:ambient-shadow hover:-translate-y-1",
  secondary: "glass border border-primary/20 text-primary px-8 py-4 rounded-lg hover:bg-white/80",
  tertiary: "text-primary hover:underline underline-offset-8 decoration-2 px-2"
}

const isLink = computed(() => !!props.href)
const componentType = computed(() => isLink.value ? 'a' : 'button')
</script>

<template>
  <component
    :is="componentType"
    :href="href"
    :id="id"
    :class="[baseClass, variantClasses[variant]]"
  >
    <slot />
  </component>
</template>
