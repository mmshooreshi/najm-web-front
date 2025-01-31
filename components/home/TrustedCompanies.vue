<template>
    <section class="py-12" aria-label="Trusted Companies">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <h2 class="text-2xl md:text-3xl font-bold text-gray-900 dark:text-gray-100 mb-8">
                مورد اعتماد شرکت‌های بزرگ و کوچک
            </h2>
            <div class="grid grid-cols-3 md:grid-cols-5 gap-6 justify-items-center">
                <div v-for="(company, index) in companies" :key="index"
                    class="w-24 h-24 flex items-center justify-center">
                    <img :src="company.logo" :alt="company.name"
                        class="object-contain w-full h-full grayscale hover:grayscale-0 transition duration-200" />
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
interface Company {
    name: string
    logo: string
}

defineProps<{
    companies: Company[]
}>()
</script>