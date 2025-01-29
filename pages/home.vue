<!-- File: pages/index.vue -->
<template>
    <VContainer fluid class="landing-page fill-height d-flex align-center justify-center">
      <VRow
        no-gutters
        align="center"
        justify="center"
        class="hero-section fill-height"
      >
        <!-- Left Column (Text & CTA) -->
        <VCol cols="12" md="6" lg="5" sm="6" class="py-10 py-md-0">
          <!-- Slide in the left column content -->
          <VSlideXTransition>
            <div class="mb-8 mb-md-0">
              <VRow no-gutters align="center" justify="center">
                <VCol cols="12" md="10">
                  <h1 class="text-h4 font-weight-bold text-center hero-heading mb-4">
                    یک راهکار خلاقانه برای چاپ و بسته‌بندی مورد نیاز شما
                  </h1>
                  <p class="text-center text-medium-emphasis hero-subtitle">
                    ایده تا بسته‌بندی، همه چیز با ما
                  </p>
                  <div class="d-flex justify-center mt-8">
                    <VBtn
                      color="primary"
                      size="large"
                      elevation="3"
                      class="cta-btn"
                    >
                      استعلام قیمت
                    </VBtn>
                  </div>
                </VCol>
              </VRow>
            </div>
          </VSlideXTransition>
        </VCol>
  
        <!-- Right Column (Image / Additional Info) -->
        <VCol
          class="hidden-md-and-down fill-height pr-0 pl-0 hero-image-col"
          md="6"
          lg="7"
        >
          <VFadeTransition>
            <VImg
              src="assets/images/banner.jpg"
              cover
              class="h-100 rounded-xl hero-image d-flex align-center justify-center"
            >
              <div class="hero-text-container text-center w-75 mx-auto px-4 py-6">
                <h2 class="mb-4 text-white">مشاوره تخصصی</h2>
                <p class="text-white">
                  کار با بسته‌بندی گرافیکی فقط خرید یک محصول نیست. ما در این مسیر
                  با شما همکاری می‌کنیم تا به حل مشکلات شما و ایجاد راه‌حل‌های
                  نوآورانه کمک کنیم.
                </p>
              </div>
            </VImg>
          </VFadeTransition>
        </VCol>
      </VRow>
    </VContainer>
  </template>
  
  <script setup>
  // No additional logic needed here for the example.
  // You can keep or add any Composition API logic as needed.
  </script>
  
  <style scoped>
  /* 
    We use a “soft” gradient background for the landing page.
    Adjust colors to suit your theme.
  */
  .landing-page {
    background: linear-gradient(135deg, #f7f7f7, #e8e8e8);
  }
  
  /* Hero Section Container */
  .hero-section {
    padding: 0 1rem;
    position: relative;
  }
  
  /* Headings and subtitles */
  .hero-heading {
    font-size: 2rem;
    line-height: 1.3;
  }
  .hero-subtitle {
    font-size: 1.1rem;
    color: #666;
  }
  
  /* Button Hover Effect */
  .cta-btn {
    transition: background-color 0.3s, transform 0.3s;
  }
  .cta-btn:hover {
    background-color: #1c7ed6 !important;
    transform: translateY(-2px);
  }
  
  /* Right column image styling */
  .hero-image {
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
    border-radius: 16px;
  }
  
  /* Container over the image for the text */
  .hero-text-container {
    background-color: rgba(0, 0, 0, 0.35);
    border-radius: 8px;
    backdrop-filter: blur(4px);
  }
  
  /* 
    Reduce the heading size on smaller screens
    to keep text from overflowing 
  */
  @media (max-width: 600px) {
    .hero-heading {
      font-size: 1.6rem;
    }
  }
  </style>
  