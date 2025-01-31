<template>
  <div class="min-h-screen  flex flex-col items-center">
    <HeaderBar/>
    <!-- Navbar -->
    <nav class="w-full bg-white shadow-md p-4 rounded-lg flex justify-between items-center">
      <div class="flex items-center gap-2">
        <img src="/assets/images/najm-logo.svg" alt="Logo" class="w-6 h-6" />
        <span class="text-lg font-semibold">چاپ و بسته‌بندی نجم</span>
      </div>
      <div class="flex space-x-6 rtl:space-x-reverse text-gray-700">
        <a href="#">کاتالوگ</a>
        <a href="#">فایل‌های راهنما</a>
        <a href="#">درباره ما</a>
        <a href="#">تماس با ما</a>
      </div>
      <div class="relative">
        <input type="text" placeholder="جستجو..." class="border p-2 rounded-md focus:ring focus:ring-gray-300 w-40" />
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="w-full mt-10 bg-gray-300 p-8 rounded-lg max-w-5xl text-right rtl relative">
      <h1 class="text-3xl font-bold">یک راهکار خلاقانه برای چاپ و بسته‌بندی مورد نیاز شما</h1>
      <p class="text-gray-700 mt-4">ایده تا بسته‌بندی، همه چیز با ما</p>

      <div class="mt-6 bg-green-300 p-6 rounded-lg w-3/4 shadow-md">
        <p class="text-gray-800 text-lg">
          کار با بسته بندی گرافیکی فقط خرید یک محصول نیست. ما در این مسیر با شما همکاری می‌کنیم تا به حل مشکلات
          شما و ایجاد راه حل های نوآورانه کمک کنیم.
        </p>
      </div>
      <p class="text-md text-gray-800 mt-6">برای بیش از ۳۰ سال، ما پروژه‌های چاپی را درست و به موقع تحویل داده‌ایم.</p>
      
      <button class="mt-8 bg-green-700 text-white px-5 py-3 rounded-lg shadow-md">درخواست پروژه</button>
    </section>
  </div>
</template>

<script setup lang="ts">
import HeaderBar from "~/components/home/HeaderBar.vue"

// No additional logic required for this UI component
</script>

<style>
body {
  direction: rtl;
  text-align: right;
}
</style>