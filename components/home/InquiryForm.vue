<template>
    <section class="py-12" aria-label="Project Inquiry Form">
        <div class="max-w-lg mx-auto bg-gray-100 dark:bg-gray-800 rounded-lg p-6 shadow">
            <h2 class="text-2xl font-bold text-gray-900 dark:text-gray-100 mb-6">
                برای شروع پروژه‌ی جدید آماده‌ایم
            </h2>
            <form @submit.prevent="submitForm" class="space-y-4">
                <!-- Name -->
                <div>
                    <label for="name" class="block text-gray-700 dark:text-gray-300 mb-1">
                        نام
                    </label>
                    <input id="name" v-model="formData.name" type="text" required class="w-full rounded border border-gray-300 dark:border-gray-700 
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white" />
                </div>

                <!-- Phone Number -->
                <div>
                    <label for="phone" class="block text-gray-700 dark:text-gray-300 mb-1">
                        شماره موبایل
                    </label>
                    <input id="phone" v-model="formData.phone" type="tel" required class="w-full rounded border border-gray-300 dark:border-gray-700 
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white" />
                </div>

                <!-- Email -->
                <div>
                    <label for="email" class="block text-gray-700 dark:text-gray-300 mb-1">
                        ایمیل
                    </label>
                    <input id="email" v-model="formData.email" type="email" required class="w-full rounded border border-gray-300 dark:border-gray-700 
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white" />
                </div>

                <!-- Message -->
                <div>
                    <label for="message" class="block text-gray-700 dark:text-gray-300 mb-1">
                        پیام
                    </label>
                    <textarea id="message" v-model="formData.message" rows="3" class="w-full rounded border border-gray-300 dark:border-gray-700
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white"></textarea>
                </div>

                <!-- File Upload -->
                <div>
                    <label class="block text-gray-700 dark:text-gray-300 mb-1">
                        آپلود فایل
                    </label>
                    <input type="file" @change="handleFileUpload" class="block w-full text-sm text-gray-900 bg-gray-50 
                     border border-gray-300 rounded-lg cursor-pointer 
                     dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400" />
                </div>

                <!-- Service Selection -->
                <div>
                    <label for="service" class="block text-gray-700 dark:text-gray-300 mb-1">
                        انتخاب سرویس
                    </label>
                    <select id="service" v-model="formData.service" class="w-full rounded border border-gray-300 dark:border-gray-700 
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white">
                        <option v-for="(service, index) in services" :key="index" :value="service">
                            {{ service }}
                        </option>
                    </select>
                </div>

                <!-- Quantity -->
                <div>
                    <label for="quantity" class="block text-gray-700 dark:text-gray-300 mb-1">
                        تعداد
                    </label>
                    <input id="quantity" v-model.number="formData.quantity" type="number" min="1" class="w-full rounded border border-gray-300 dark:border-gray-700 
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white" />
                </div>

                <!-- Timeline -->
                <div>
                    <label for="timeline" class="block text-gray-700 dark:text-gray-300 mb-1">
                        زمان تحویل
                    </label>
                    <select id="timeline" v-model="formData.timeline" class="w-full rounded border border-gray-300 dark:border-gray-700 
                     px-3 py-2 focus:outline-none dark:bg-gray-700 dark:text-white">
                        <option value="1-week">۱ هفته</option>
                        <option value="2-weeks">۲ هفته</option>
                        <option value="1-month">۱ ماه</option>
                    </select>
                </div>

                <!-- Submit -->
                <button type="submit" class="block w-full bg-blue-600 hover:bg-blue-700 text-white 
                   font-semibold px-4 py-2 rounded focus:outline-none 
                   transition-colors duration-200">
                    ارسال درخواست
                </button>
            </form>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, defineEmits, defineProps } from 'vue'

const emits = defineEmits(['form-submit'])

const props = defineProps<{
    services: string[]
}>()

const formData = ref({
    name: '',
    phone: '',
    email: '',
    message: '',
    file: null as File | null,
    service: '',
    quantity: 1,
    timeline: '1-week',
})

function handleFileUpload(e: Event) {
    const target = e.target as HTMLInputElement
    if (target.files && target.files.length > 0) {
        formData.value.file = target.files[0]
    }
}

function submitForm() {
    emits('form-submit', { ...formData.value })
}
</script>