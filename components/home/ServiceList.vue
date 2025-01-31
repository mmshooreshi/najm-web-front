<template>
    <section class="py-12" aria-label="Service List">
      <div class="max-w-7xl mx-auto px-4">
        <!-- Heading -->
        <div class="text-center mb-8">
          <h2 class="text-3xl font-bold text-gray-900 dark:text-gray-100">
            مشاوره تخصصی
          </h2>
          <p class="text-gray-600 dark:text-gray-300">
            دقیق، کارآمد، بدون واسطه
          </p>
        </div>
  
        <!-- Services Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
          <div
            v-for="(service, index) in services"
            :key="index"
            class="p-6 bg-white dark:bg-gray-800 rounded shadow hover:shadow-lg
                   transition transform hover:scale-105 cursor-pointer"
            @click="goToService(service.link)"
          >
            <img
              :src="service.icon"
              alt=""
              class="h-12 w-12 mb-4 object-contain"
            />
            <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-2">
              {{ service.title }}
            </h3>
            <p class="text-gray-600 dark:text-gray-300 mb-4">
              {{ service.description }}
            </p>
            <NuxtLink
              :to="service.link"
              class="inline-block bg-blue-600 text-white px-3 py-1 rounded hover:bg-blue-700"
            >
              بیشتر بدانید
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup lang="ts">
  import { defineProps } from 'vue'
  import { useRouter } from '#imports'
  
  interface Service {
    icon: string
    title: string
    description: string
    link: string
  }
  
  const props = defineProps<{
    services: Service[]
  }>()
  
  const router = useRouter()
  
  function goToService(link: string) {
    router.push(link)
  }
  </script>
  