<template>
    <section class="w-full py-12 bg-gray-100 dark:bg-gray-900" aria-label="Hero Section">
      <div class="max-w-7xl mx-auto px-4 flex flex-col items-center text-center md:text-left md:flex-row md:justify-between">
        
        <!-- Left: Hero Text -->
        <div class="max-w-lg">
          <h1 class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-gray-100 leading-snug">
            {{ title }}
          </h1>
          <p class="text-lg text-gray-700 dark:text-gray-300 mt-3">
            {{ subtitle }}
          </p>
          <button 
            @click="requestProject" 
            class="mt-6 bg-green-600 hover:bg-green-700 text-white font-semibold px-5 py-2.5 rounded-lg 
            transition-colors duration-200 focus:outline-none shadow-md">
            {{ ctaButtonText }}
          </button>
        </div>
  
        <!-- Right: Floating CTA Box -->
        <div class="relative bg-green-100 dark:bg-green-700 p-4 rounded-lg shadow-lg mt-8 md:mt-0 md:max-w-sm">
          <p class="text-gray-800 dark:text-gray-100 text-sm">
            {{ ctaText }}
          </p>
        </div>
        
      </div>
    </section>
  </template>
  
  <script setup lang="ts">
  import { defineEmits, defineProps } from 'vue'
  
  const emits = defineEmits(['request-project'])
  
  function requestProject() {
      emits('request-project')
  }
  
  defineProps<{
      title: string
      subtitle: string
      ctaText: string
      ctaButtonText: string
  }>()
  </script>
  