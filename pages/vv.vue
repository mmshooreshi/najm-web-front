<template>
    <div class="min-h-[90vh] w-[90vw] flex flex-col items-center mt-1 px-auto mx-auto">
      <!-- Header -->
      <HeaderBar />
  
      <!-- Navigation Bar -->
      <nav class=" w-full py-4 mt-2">
        <div class="mx-2 flex flex-wrap items-center justify-between">
          <!-- Right Section (Services & Categories) -->
          <div class="flex flex-row-reverse space-x-2">

            <div class="flex items-center bg-white hover:bg-gray-200 pl-2 px-1 py-[5.5px] cursor-pointer rounded-xl border border-0 border-solid border-gray-500/20">
                <span class="mx-2 mb-1 text-gray-500 leading-tight text-xs	">دسته‌بندی</span>
                <ChevronDown :size="16" color="#6b6b6b" :stroke-width="1.25" absoluteStrokeWidth />
            </div>


            <div class="flex items-center bg-white hover:bg-gray-200 pr-2 px-1 py-[5.5px] cursor-pointer rounded-xl border border-0 border-solid border-gray-500/20">
                <Menu :size="16" color="#6b6b6b" :stroke-width="2" absoluteStrokeWidth />
                <span class="mx-2 mb-1 text-gray-500 leading-tight text-xs	">خدمات</span>
            </div>

        </div>
  
          <!-- Center Section (Main Navigation) -->
          <div class="hidden md:flex md:flex-row-reverse space-x-6 items-center align-middle">
            <!-- Search Button -->
            <div class="border border-transparent hover:bg-gray-200 hover:border-gray-300 text-center p-1 pb-0 px-2 cursor-pointer rounded-xl bg-white shadow-sm">
                <Search :size="18" color="#6b6b6b" :stroke-width="1.5" />
            </div>
            <div class="h-min text-gray-500 hover:text-black text-xs cursor-pointer text-center">تماس با ما</div>
            <div class="h-min text-gray-500 hover:text-black text-xs cursor-pointer text-center">درباره ما</div>
            <div class="h-min text-gray-500 hover:text-black text-xs cursor-pointer text-center">فایل‌های راهنما</div>
            <div class="h-min text-gray-500 hover:text-black text-xs cursor-pointer text-center">کاتالوگ</div>
  

        </div>

        </div>
      </nav>
  
      <!-- Hero Section -->
      <div class="p-8 w-[91%] pb-16 flex flex-col md:flex-row items-center greeeen rounded-3xl">
        <!-- Hero Text -->
        <div class="md:w-1/2 text-right">
          <div class="text-3xl text-gray-800">راهکاری خلاقانه برای چاپ و بسته‌بندی</div>
          <div class="text-gray-700 mt-2">ایده تا بسته‌بندی، همه چیز با ما</div>
          <!-- <button class="mt-6 px-6 py-3 bg-green-700 text-white rounded-md hover:bg-green-800 transition">
            درخواست پروژه
          </button> -->
        </div>
  
        <!-- Hero Image Placeholder -->
        <!-- <div class="md:w-1/2 mt-6 md:mt-0 flex justify-center">
          <img src="https://picsum.photos/seed/hero/400/250" class="rounded-lg shadow-lg" />
        </div> -->
      </div>
  
      <!-- Information Card -->
      <!-- <section class="container mx-auto px-6 py-10">
        <div class="bg-green-100 p-6 rounded-lg text-right shadow-md max-w-3xl mx-auto">
          <p class="text-gray-800 font-bold text-lg">
            بیش از ۳۰ سال تجربه در چاپ و بسته‌بندی
          </p>
          <p class="text-gray-600 mt-2">
            کار با بسته‌بندی گرافیکی فقط خرید یک محصول نیست. ما همراه شما هستیم تا بهترین راهکارهای نوآورانه را ارائه دهیم.
          </p>
        </div>
      </section> -->
  
      <!-- Pagination Dots -->
      <!-- <div class="flex space-x-2 mt-6">
        <span class="w-3 h-3 bg-gray-400 rounded-full"></span>
        <span class="w-3 h-3 bg-black rounded-full"></span>
        <span class="w-3 h-3 bg-gray-400 rounded-full"></span>
      </div> -->
    </div>
  </template>
  
  <script setup>
  import HeaderBar from '~/components/home/HeaderBar.vue';
  import { Search } from 'lucide-vue-next';

  import { Menu,ChevronDown } from 'lucide-vue-next';

  </script>
  