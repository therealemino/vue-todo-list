<template>

<div class="container p-8 sm:px-8 sm:py-2 flex justify-between bg-gray-500 dark:bg-navbar-brown max-w-full transition-2000 sticky">
    <img src="../assets/logo.png" class="hidden md:inline-block" alt="" v-if="darkMode === true">
    <img src="../assets/logo-light.png" class="hidden md:inline-block" alt="" v-if="!darkMode === true">
    <h1 class="text-gray-900 dark:text-navbar-cream text-xl lg:text-3xl my-auto">Vue Todo List App</h1>
    <div class="flex w-1/4 md:w-3/8 lg:w-1/5 justify-end">
        <Socials class="dark:text-navbar-cream my-auto hidden sm:flex" />
        <span
        role="checkbox"
        :aria-checked="darkMode"
        tabindex="0"
        @click="changeDarkMode"
        :class="darkMode ? 'bg-gray-300' : 'bg-navbar-brown'"
        class="relative inline-block flex-shrink-0 h-6 w-11 border-2 border-transparent rounded-full cursor-pointer transition-colors ease-in-out duration-200 focus:outline-none focus:shadow-outline my-auto"
    >
        <span
        aria-hidden="true"
        :class="darkMode ? 'translate-x-5' : 'translate-x-0'"
        class="inline-block h-5 w-5 rounded-full bg-white dark:bg-navbar-cream shadow transform transition ease-in-out duration-200 text-gray-300"
        ></span>
    </span>
    </div>


</div>


</template>

<script>
import Socials from './Socials.vue'
  export default {
      'Name': 'Navbar',
      components: { Socials },
      props: ['darkMode','changeDarkMode']
  }
</script>
