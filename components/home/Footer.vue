<template>
    <footer class="bg-gray-900 text-white py-8" aria-label="Footer">
        <div class="max-w-7xl mx-auto px-4 grid grid-cols-1 sm:grid-cols-3 gap-6">
            <!-- Company Info -->
            <div>
                <h3 class="text-lg font-semibold mb-3">درباره ما</h3>
                <p class="text-sm text-gray-300">
                    {{ companyInfo }}
                </p>
            </div>

            <!-- Quick Links -->
            <div>
                <h3 class="text-lg font-semibold mb-3">لینک‌های سریع</h3>
                <ul class="space-y-2">
                    <li v-for="(link, index) in quickLinks" :key="index" class="hover:font-bold">
                        <NuxtLink :to="link.link">
                            {{ link.title }}
                        </NuxtLink>
                    </li>
                </ul>
            </div>

            <!-- Contact Details -->
            <div>
                <h3 class="text-lg font-semibold mb-3">ارتباط با ما</h3>
                <ul class="space-y-2 text-sm text-gray-300">
                    <li v-if="contactDetails.address">
                        <span class="font-medium">آدرس: </span>{{ contactDetails.address }}
                    </li>
                    <li v-if="contactDetails.phone">
                        <span class="font-medium">تلفن: </span>{{ contactDetails.phone }}
                    </li>
                    <li v-if="contactDetails.email">
                        <span class="font-medium">ایمیل: </span>{{ contactDetails.email }}
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<script setup lang="ts">
interface QuickLink {
    title: string
    link: string
}

interface ContactDetails {
    address?: string
    phone?: string
    email?: string
}

defineProps<{
    companyInfo: string
    quickLinks: QuickLink[]
    contactDetails: ContactDetails
}>()
</script>