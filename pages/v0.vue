<template>
<HeroSection :title="heroTitle" :subtitle="heroSubtitle" :ctaText="heroCtaText" :ctaButtonText="heroCtaButtonText"
@request-project="handleRequestProject" />
</template>

<script setup lang="ts">
/**
 * Nuxt 3 Composables
 */
import { ref } from 'vue'
import { useColorMode } from '#imports'

/**
 * Import Components (Auto-import is also possible if configured)
 * Adjust the paths if your directory structure differs.
 */
import Header from '~/components/home/Header.vue'
import Hero from '~/components/home/Hero.vue'
import HeroSection from '~/components/home/HeroSection.vue'

import ServiceList from '~/components/home/ServiceList.vue'
import ProductCarousel from '~/components/home/ProductCarousel.vue'
import CustomPackaging from '~/components/home/CustomPackaging.vue'
import InquiryForm from '~/components/home/InquiryForm.vue'
import TrustedCompanies from '~/components/home/TrustedCompanies.vue'
import Footer from '~/components/home/Footer.vue'

/** ------------------
 * Dark Mode
 * ------------------- */
const colorMode = useColorMode()
function toggleDarkMode() {
    colorMode.value = colorMode.value === 'dark' ? 'light' : 'dark'
}

/** ------------------
 * Header Props
 * ------------------- */
const logoSrc = '/images/logo.png'
const menuItems = ref([
    { title: 'خانه', link: '/' },
    { title: 'خدمات', link: '/services' },
    { title: 'محصولات', link: '/products' },
    { title: 'تماس با ما', link: '/contact' }
])

/** ------------------
 * Hero Props
 * ------------------- */
const heroTitle = 'انقلابی در بسته‌بندی و چاپ'
const heroSubtitle = 'با نوآوری‌های جدید، فراتر از مرزها چاپ کنید.'
const heroCtaText = 'کسب و کار شما شایسته بهترین کیفیت چاپ و بسته‌بندی است.'
const heroCtaButtonText = 'شروع پروژه'

function handleRequestProject() {
    // Could open a modal, navigate to form, etc.
    alert('درخواست پروژه جدید')
}

/** ------------------
 * Service List Props
 * ------------------- */
const services = ref([
    {
        icon: '/images/icons/consulting.svg',
        title: 'مشاوره چاپ',
        description: 'مشاوره‌های تخصصی برای بهترین نتایج چاپ.',
        link: '/services/consulting'
    },
    {
        icon: '/images/icons/design.svg',
        title: 'طراحی بسته‌بندی',
        description: 'طراحی جذاب برای محصولات مختلف.',
        link: '/services/design'
    },
    {
        icon: '/images/icons/printing.svg',
        title: 'چاپ دیجیتال',
        description: 'چاپ سریع و با کیفیت بالا.',
        link: '/services/digital-printing'
    },
    {
        icon: '/images/icons/offset.svg',
        title: 'چاپ افست',
        description: 'تیراژ بالا با هزینه مناسب.',
        link: '/services/offset-printing'
    }
])

/** ------------------
 * Product Carousel Props
 * ------------------- */
const productBoxes = ref([
    { image: '/images/box1.jpg', title: 'جعبه هدیه' },
    { image: '/images/box2.jpg', title: 'جعبه پیتزا' },
    { image: '/images/box3.jpg', title: 'جعبه شیرینی' },
    { image: '/images/box4.jpg', title: 'جعبه دارو' },
    { image: '/images/box5.jpg', title: 'جعبه سفارشی' }
])

function handleBoxClick(box: { image: string; title: string }) {
    alert(`Box clicked: ${box.title}`)
}

/** ------------------
 * Custom Packaging Props
 * ------------------- */
const customPackages = ref([
    {
        image: '/images/custom1.jpg',
        title: 'جعبه خاص فانتزی',
        subtitle: 'مناسب برای محصولات لاکچری'
    },
    {
        image: '/images/custom2.jpg',
        title: 'جعبه محافظتی',
        subtitle: 'ایده‌آل برای حمل و نقل'
    },
    {
        image: '/images/custom3.jpg',
        title: 'جعبه چاپ اختصاصی',
        subtitle: 'مناسب برای برندسازی'
    },
    {
        image: '/images/custom4.jpg',
        title: 'جعبه هدیه شخصی‌سازی‌شده',
        subtitle: 'مناسب برای رویدادهای خاص'
    }
])

/** ------------------
 * Inquiry Form Props
 * ------------------- */
const inquiryServices = ref(['طراحی', 'چاپ دیجیتال', 'چاپ افست', 'بسته‌بندی'])

function handleFormSubmit(formData: any) {
    console.log('Form data:', formData)
    alert(`درخواست ثبت شد: ${formData.name}`)
}

/** ------------------
 * Trusted Companies Props
 * ------------------- */
const trustedCompanies = ref([
    { name: 'Company A', logo: '/images/logos/company-a.png' },
    { name: 'Company B', logo: '/images/logos/company-b.png' },
    { name: 'Company C', logo: '/images/logos/company-c.png' },
    { name: 'Company D', logo: '/images/logos/company-d.png' },
    { name: 'Company E', logo: '/images/logos/company-e.png' }
])

/** ------------------
 * Footer Props
 * ------------------- */
const companyInfo = 'شرکت ما با سال‌ها تجربه در زمینه‌ی چاپ و بسته‌بندی آماده‌ی خدمت‌رسانی به شماست.'
const quickLinks = ref([
    { title: 'درباره ما', link: '/about' },
    { title: 'خدمات', link: '/services' },
    { title: 'محصولات', link: '/products' },
    { title: 'وبلاگ', link: '/blog' }
])
const contactDetails = {
    address: 'تهران، خیابان آزادی، پلاک ۲۰',
    phone: '۰۲۱-۱۲۳۴۵۶۷۸',
    email: 'info@najmprint.com'
}
</script>

<style scoped>
/* Basic styling adjustments. Tailwind handles most layout & responsiveness. */
</style>