<template>
    <section class="py-12" aria-label="Custom Packaging Grid">
        <div class="max-w-7xl mx-auto px-4">
            <!-- Header -->
            <h2 class="text-2xl md:text-3xl font-bold text-center mb-8 text-gray-900 dark:text-gray-100">
                توی نجم هر ایده‌ای رو میشه چاپ کرد!
            </h2>

            <!-- Packages Grid -->
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <div v-for="(pkg, index) in packages" :key="index" class="bg-white dark:bg-gray-800 p-4 rounded shadow cursor-pointer 
                   hover:shadow-lg transition transform hover:-rotate-1" @click="goToPackageDetails(pkg)">
                    <img :src="pkg.image" :alt="pkg.title" class="w-full h-32 object-cover rounded mb-4" />
                    <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-100 mb-1">
                        {{ pkg.title }}
                    </h3>
                    <p class="text-gray-600 dark:text-gray-300">
                        {{ pkg.subtitle }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { useRouter } from '#imports'
import { defineProps } from 'vue'

interface PackageItem {
    image: string
    title: string
    subtitle: string
}

const props = defineProps<{
    packages: PackageItem[]
}>()

const router = useRouter()

function goToPackageDetails(pkg: PackageItem) {
    // Navigate to the details page, e.g.:
    // router.push(`/packages/${slugify(pkg.title)}`)
    // Or direct link from pkg object if you store it
    router.push('/package-details')
}
</script>