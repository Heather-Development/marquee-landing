<template>
  <div class="container mx-auto px-5">
    <header class="flex justify-between items-center py-12">
      <div>
        <NuxtLink to="/">Marquee</NuxtLink>
      </div>
      <nav class="flex justify-end flex-col md:flex-row">
        <button @click="toggleMobileNav" class="btn flex md:hidden focus:outline-none">
          <Icon name="heroicons:bars-3-16-solid" size="1.5em"/>
        </button>

        <ul class="space-x-10 font-theme-heading font-medium items-center hidden md:flex flex-col space-y-7 md:space-y-0 md:flex-row">
          <li class="hover:text-theme-secondary transition duration-200"><a href="#features">Features</a></li>
          <li class="hover:text-theme-secondary transition duration-200"><a href="#faq">FAQ</a></li>
          <li class="hover:text-theme-secondary transition duration-200"><NuxtLink to="/why">Why Marquee?</NuxtLink></li>
          <li class="px-6 text-white border-2 border-transparent cursor-pointer"><NuxtLink class="btn" to="https://marquee-app.pages.dev">Play</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <div v-show="mobileNav">
      <div class="absolute px-5 py-12 block z-30 top-0 left-0 w-full h-full bg-gradient-to-b from-theme-dark-blue via-theme-dark-blue-tp to-theme-dark-blue">
        <div class="flex justify-between items-center">
          <button @click="toggleMobileNav" class="btn"><Icon name="heroicons:bars-3-16-solid" size="1.5em"/></button>
        </div>
        <ul class="text-md tracking-widest items-center flex flex-col mt-14">
          <li class="hover:text-theme-secondary transition duration-200 py-4 text-center w-full"><a @click="toggleMobileNav" href="#features">Features</a></li>
          <li class="hover:text-theme-secondary transition duration-200 py-4 text-center w-full"><a @click="toggleMobileNav" href="#faq">FAQ</a></li>
          <li class="hover:text-theme-secondary transition duration-200 py-4 text-center w-full"><NuxtLink to="/why">Why Marquee?</NuxtLink></li>
          <li class="px-6 mt-6 w-full text-center text-white border-2 border-transparent cursor-pointer"><NuxtLink class="btn" to="https://marquee-app.pages.dev">Play</NuxtLink></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
  import { ref } from 'vue';
  let mobileNav = ref(false);
  
  let toggleMobileNav = () => {
    mobileNav.value = !mobileNav.value
  }
</script>

<style>

</style>