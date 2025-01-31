<template>
  <div class="w-full flex flex-row-reverse items-center justify-between">
    <!-- User Dropdown -->
    <div class="relative">
      <div class="flex items-center hover:bg-gray-200 px-3 py-2 cursor-pointer rounded-xl hover:bg-gray-300 border border-1 border-solid border-gray-500/20">
        <UserCheck :size="20" color="#6b6b6b" :stroke-width="1.25" absoluteStrokeWidth />
        <span class="mx-2 mb-1 text-gray-500 leading-tight text-xs	">محمدمهدی</span>
        <ChevronDown :size="16" color="#6b6b6b" :stroke-width="1.25" absoluteStrokeWidth />
      </div>
    </div>

    <!-- Logo and Text -->
    <div class="flex items-center space-x-1 cursor-pointer">
      <div class="w-10 h-10 rounded-full flex items-center justify-center">
        <img src="assets/images/najm-logo.svg" alt="Logo" class="w-full h-full object-contain" />
      </div>
      <span class="text-gray-500 text-sm">چاپ و بسته‌بندی</span>
      <span class="font-bold text-gray-500 text-sm">نجم</span>
    </div>
  </div>
</template>

<script setup>
import { UserCheck,ChevronDown } from 'lucide-vue-next';
</script>