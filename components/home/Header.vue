<template>
    <header class="sticky top-0 z-50 bg-white shadow-sm dark:bg-gray-800" aria-label="Main Navigation">
      <nav class="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
        
        <!-- Left: Logo -->
        <NuxtLink href="/" aria-label="Home">
          <img :src="logoSrc" alt="Website Logo" class="h-10 w-auto object-contain cursor-pointer" />
        </NuxtLink>
  
        <!-- Right: Menu Items -->
        <div class="flex items-center space-x-6">
          <ul class="hidden md:flex items-center space-x-6">
            <li v-for="(item, index) in menuItems" :key="index" class="hover:font-bold text-gray-700 dark:text-white">
              <NuxtLink :to="item.link">
                {{ item.title }}
              </NuxtLink>
            </li>
          </ul>
  
          <!-- Request Project Button (Matches Wireframe) -->
          <button 
            type="button"
            class="bg-green-600 hover:bg-green-700 text-white px-4 py-2 rounded-lg transition-colors duration-200 focus:outline-none">
            درخواست پروژه
          </button>
        </div>
  
      </nav>
    </header>
  </template>
  
  <script setup lang="ts">
  interface MenuItem {
    title: string
    link: string
  }
  
  defineProps<{
    logoSrc: string
    menuItems: MenuItem[]
  }>()
  </script>
  