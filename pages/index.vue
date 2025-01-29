// File: pages/sign-in.vue
<template>
  <VContainer fluid class="fill-height">
    <VRow no-gutters align="center" justify="center" class="fill-height">
      <VCol cols="12" md="6" lg="5" sm="6">
        <VRow no-gutters align="center" justify="center">
          <VCol cols="12" md="10">
            <h1 class="text-h4 font-weight-bold text-center">ورود به حساب کاربری</h1>
            <p class="text-center text-medium-emphasis">برای شروع، اطلاعات خود را وارد کنید</p>

            <VForm @submit.prevent="submit" class="mt-7">
              <div class="mt-1">
                <label class="label text-grey-darken-2" for="email">ایمیل</label>
                <VTextField
                  :rules="[ruleRequired, ruleEmail]"
                  v-model="email"
                  prepend-inner-icon="fluent:mail-24-regular"
                  id="email"
                  name="email"
                  type="email"
                />
              </div>
              <div class="mt-1">
                <label class="label text-grey-darken-2" for="password">رمز عبور</label>
                <VTextField
                  :rules="[ruleRequired, rulePassLen]"
                  v-model="password"
                  prepend-inner-icon="fluent:password-20-regular"
                  id="password"
                  name="password"
                  type="password"
                />
              </div>
              <div class="mt-5">
                <VBtn type="submit" block min-height="44" class="gradient primary">ورود</VBtn>
              </div>
            </VForm>
            <p class="text-body-2 mt-10">
              <NuxtLink to="/reset-password" class="font-weight-bold text-primary"
                >فراموشی رمز عبور؟</NuxtLink
              >
            </p>
            <p class="text-body-2 mt-4">
              <span
                >حساب کاربری ندارید؟
                <NuxtLink to="/signup" class="font-weight-bold text-primary"
                  >ثبت نام کنید</NuxtLink
                ></span
              >
            </p>
          </VCol>
        </VRow>
      </VCol>
      <VCol class="hidden-md-and-down fill-height" md="6" lg="7">
        <VImg
          src="/images/printing-banner.jpg"
          cover
          class="h-100 rounded-xl d-flex align-center justify-center"
        >
          <div class="text-center w-50 text-white mx-auto">
            <h2 class="mb-4">شروع سفارش چاپ و بسته‌بندی</h2>
            <p>
              با ورود به حساب خود، می‌توانید سفارش‌های چاپ و بسته‌بندی خود را مدیریت کنید و به خدمات اختصاصی نجــم دسترسی داشته باشید.
            </p>
          </div>
        </VImg>
      </VCol>
    </VRow>
  </VContainer>
</template>

<script setup>
const email = ref("");
const password = ref("");

const { ruleEmail, rulePassLen, ruleRequired } = useFormRules();

const submit = async () => {};
</script>

<style scoped>
.fill-height {
  min-height: 100vh;
}
</style>