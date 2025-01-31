<template>
    <section class="py-12" aria-label="Product Categories Carousel">
      <div class="max-w-7xl mx-auto px-4">
        <!-- Section Title -->
        <h2 class="text-2xl font-bold text-gray-900 dark:text-gray-100 mb-4">
          دسته‌بندی محصولات
        </h2>
  
        <!-- Carousel Container -->
        <div class="relative">
          <!-- Left Button -->
          <button
            @click="scrollLeft"
            aria-label="Scroll Left"
            class="absolute left-0 top-1/2 -translate-y-1/2 bg-gray-200 dark:bg-gray-700
                   p-2 rounded-full hover:bg-gray-300 dark:hover:bg-gray-600 z-10"
          >
            ◀
          </button>
  
          <!-- Scrollable Area -->
          <div 
            ref="carouselRef"
            class="flex gap-4 overflow-x-auto scroll-smooth py-2 px-8"
          >
            <div
              v-for="(box, index) in boxes"
              :key="index"
              class="min-w-[200px] bg-white dark:bg-gray-800 rounded shadow p-4 flex flex-col
                     items-center justify-between shrink-0"
            >
              <img
                :src="box.image"
                :alt="box.title"
                class="w-full h-32 object-cover mb-2 rounded"
              />
              <h3 class="text-base font-semibold text-gray-800 dark:text-gray-100 mb-2">
                {{ box.title }}
              </h3>
              <button
                @click="handleBoxClick(box)"
                class="bg-blue-600 text-white px-3 py-1 rounded hover:bg-blue-700
                       transition-colors duration-200"
              >
                مشاهده ابعاد
              </button>
            </div>
          </div>
  
          <!-- Right Button -->
          <button
            @click="scrollRight"
            aria-label="Scroll Right"
            class="absolute right-0 top-1/2 -translate-y-1/2 bg-gray-200 dark:bg-gray-700
                   p-2 rounded-full hover:bg-gray-300 dark:hover:bg-gray-600 z-10"
          >
            ▶
          </button>
        </div>
      </div>
    </section>
  </template>
  
  <script setup lang="ts">
  import { ref, defineEmits, defineProps } from 'vue'
  
  const carouselRef = ref<HTMLElement | null>(null)
  
  const emits = defineEmits(['box-click'])
  
  interface Box {
    image: string
    title: string
  }
  
  const props = defineProps<{
    boxes: Box[]
  }>()
  
  function handleBoxClick(box: Box) {
    emits('box-click', box)
  }
  
  function scrollLeft() {
    if (carouselRef.value) {
      carouselRef.value.scrollBy({ left: -300, behavior: 'smooth' })
    }
  }
  
  function scrollRight() {
    if (carouselRef.value) {
      carouselRef.value.scrollBy({ left: 300, behavior: 'smooth' })
    }
  }
  </script>
  