<template>
    <section class="w-full py-12 bg-gray-100 dark:bg-gray-900 rtl" aria-label="Hero Section">
      <div class="max-w-7xl mx-auto px-4 flex flex-col items-center md:flex-row md:justify-between space-y-6 md:space-y-0">
  
        <!-- Left: Hero Text -->
        <div class="max-w-lg text-center md:text-right">
          <h1 class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-gray-100 leading-snug">
            {{ title }}
          </h1>
          <p class="text-lg text-gray-700 dark:text-gray-300 mt-3">
            {{ subtitle }}
          </p>
        </div>
  
        <!-- Right: Floating CTA Box & Large Background -->
        <div class="relative flex-1 flex flex-col justify-end items-start bg-red-300 rounded-lg shadow-lg p-6 md:min-h-[350px] w-full">
          
          <!-- Floating Green Box -->
          <div class="absolute bottom-8 right-6 bg-green-200 dark:bg-green-700 p-4 rounded-lg shadow-md w-64">
            <p class="text-gray-800 dark:text-gray-100 text-sm">
              {{ ctaText }}
            </p>
          </div>
  
          <!-- Call to Action Button -->
          <NuxtLink 
            to="/request-project"
            class="absolute bottom-6 left-6 bg-green-800 hover:bg-green-900 text-white font-semibold px-5 py-2.5 rounded-lg 
            transition-colors duration-200 focus:outline-none shadow-md">
            {{ ctaButtonText }}
          </NuxtLink>
  
          <!-- Carousel Indicators -->
          <div class="absolute bottom-2 left-1/2 transform -translate-x-1/2 flex space-x-1">
            <span class="w-2 h-2 bg-gray-500 rounded-full"></span>
            <span class="w-2 h-2 bg-gray-300 rounded-full"></span>
            <span class="w-2 h-2 bg-gray-300 rounded-full"></span>
          </div>
  
        </div>
      </div>
    </section>
  </template>
  
  <script setup lang="ts">
  import { defineProps } from 'vue'
  
  defineProps<{
      title: string
      subtitle: string
      ctaText: string
      ctaButtonText: string
  }>()
  </script>
  
  <style scoped>
  /* RTL support */
  .rtl {
    direction: rtl;
    text-align: right;
  }
  </style>
  