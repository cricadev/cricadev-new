<script setup lang="ts">
import { useCycleList } from '@vueuse/core'
import { watchEffect } from 'vue-demi'
const colorMode = useColorMode()

const { state, next } = useCycleList(['dark', 'light', 'system'])
const icon = computed(() => {
  if (state.value === 'dark') return 'i-heroicons-moon-20-solid'
  if (state.value === 'light') return 'i-heroicons-sun-20-solid'
  if (state.value === 'system') return 'i-heroicons-computer-desktop-20-solid'
})
watchEffect(() => colorMode.preference = state.value as any)
</script>

<template>
  <ClientOnly>
    <UButton :icon="icon" color="gray" variant="ghost" aria-label="Theme" @click="next()" />
    <template #fallback>
      <div class="w-8 h-8" />
    </template>
  </ClientOnly>
</template>
