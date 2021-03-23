<template>
<footer class="">
  <div class="mt-32 p-10 sm:p-5 sm:grid sm:grid-cols-12 bg-gray-500 dark:bg-navbar-brown dark:text-navbar-cream mx-auto">
        <div class="col-span-2 col-start-2  col-end-4">
            <img src="../assets/emino.png" class="object-fit h-24 lg:h-36 rounded-full" alt="Image of Emino">
        </div>
        <div class="col-start-4 col-span-6 px-2">
            <h3 class="text-2xl lg:text-3xl mt-1">Emino</h3>
            <p class="text-md lg:text-lg">Student of University of Nigeria | Front-end Web Developer (React, Vue) | Data Science enthusiast | Head of NexLearn - a subsidiary of Nexbuy District </p>
        </div>

        <div class="col-start-2 col-span-5 justify-end">
        <Socials />
    </div>    
  </div>
</footer>


</template>

<script>
import Socials from './Socials'

export default {
    'Name': 'Footer',
    components: { Socials }

}
</script>

<style>

</style>