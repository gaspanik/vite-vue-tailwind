<script setup lang="ts">
defineProps<{ msg: string }>()
import { CodeSquare } from 'lucide-vue-next'
</script>

<template>
  <div class="flex flex-col justify-center items-center bg-white min-h-screen">
    <div class="flex flex-col items-start gap-1">
      <div class="flex items-center gap-2">
        <CodeSquare class="w-6 h-6" />
        <h1 class="font-medium text-xl">{{ msg }}</h1>
      </div>
      <p class="text-gray-600">
        Check out
        <a class="text-teal-600" href="https://vuejs.org/guide/quick-start.html#local" target="_blank">create-vue</a>, the official Vue + Vite starter
      </p>
    </div>
  </div>
</template>

<style scoped>
/* scoped styles here */
</style>
