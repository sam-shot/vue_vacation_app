<script setup>
import { ref } from 'vue';

const links = ['Home', 'About', 'Tours', 'Blog'];
const countries = [
  {
    'label': "@Nigeria",
    "colorF": "from-green-100",
    "colorT": "to-green-400",
    "dColorF": "dark:from-green-700",
    "dColorT": "dark:to-green-900",
  },
  {
    'label': "@California",
    "colorF": "from-orange-200",
    "colorT": "to-yellow-400",
    "dColorF": "dark:from-orange-600",
    "dColorT": "dark:to-yellow-800",
  },
  {
    'label': "@Italy",
    "colorF": "from-red-200",
    "colorT": "to-red-400",
    "dColorF": "dark:from-red-700",
    "dColorT": "dark:to-red-900",
  },
  {
    'label': "...e.t.c",
    "colorF": "from-blue-100",
    "colorT": "to-blue-300",
    "dColorF": "dark:from-blue-800",
    "dColorT": "dark:to-blue-950",
  }
];
const isDark = ref(true);
const showModal = ref(false);
</script>

<template>
  <div :class="{ dark: isDark }">
    <div
      class="  dark:bg-gradient-to-b dark:from-[#0d232cfc] dark:to-[#09153b]  sm:w-screen  scroll-smooth bg-gradient-to-b from-cyan-50 to-blue-50 dark:text-white text-gray-800  sm:px-20">


      <div
        class="flex flex-row justify-between items-center py-3 sm:py-5 sm:mx-32 px-5 fixed left-0 right-0 backdrop-blur-lg z-5">
        <span class="font-bold text-3xl">Mr. Tour</span>
        <div class="sm:inline hidden font-semibold text-gray-700">
          <span v-for="link in links" class="mx-1 px-4 py-2 hover:bg-gray-200 rounded-lg duration-200 ease-in">{{ link
          }}</span>
        </div>
        <div class="inline-flex items-center">
          <button @click="isDark = !isDark"
            class="p-1.5 dark:bg-opacity-40 bg-opacity-40 dark:bg-cyan-950 dark:text-white bg-cyan-50 rounded-lg flex flex-row shadow-2xl border border-blue-100 font-bold text-gray-600 justify-center items-center">
            <div class="px-2 py-1 " :class="{ darkToggle: isDark }"> <i class="uil uil-moon"></i></div>
            <div class="px-2 py-1" :class="{ darkToggle: !isDark }">
              <i class="uil uil-sun"></i>
            </div>
          </button>
          <button @click="showModal = !showModal"
            class="sm:hidden ml-4 px-2 py-1.5 rounded-lg shadow-xl  dark:bg-opacity-40 bg-opacity-40 dark:shadow-md dark:bg-cyan-950 bg-cyan-50 dark:border-00 border border-blue-100">
            <i v-if="!showModal" class="uil uil-bars text-2xl"></i>
            <i v-else class="uil uil-multiply text-2xl"></i>
          </button>
        </div>
      </div>

      <!-- MODAL -->

      <div v-if="showModal"
        class="backdrop-blur-xl  bg-opacity-40 w-full fixed top-[4.25rem] flex flex-col justify-between p-10 pb-32 h-full">
        <div class="flex flex-col font-semibold ">
          <span 
          v-for="link in links" 
          @click="showModal = false"
          class="mx-1 px-4 py-2 hover: dark:hover:bg-cyan-900 hover:bg-cyan-100 rounded-lg duration-100 ease-in">{{ link
          }}</span>
        </div>
        <button
          class="ring  ring-blue-300 dark:ring-0 rounded-lg py-3 px-8 dark:bg-teal-600 bg-black font-bold dark:text-white text-blue-50 shadow-2xl">Sign
          in</button>

      </div>

      <!-- MODAL END -->



      <div class="flex flex-row sm:justify-between justify-center pt-24 px-5">
        <div class="sm:w-2/6 text-center sm:text-start mb-20">
          <h1 class="pb-4 font-extrabold text-6xl leading-[5rem]">Let's make <br> your <span
              class="text-teal-700 dark:text-teal-500">dream</span> <br>vacation.</h1>
          <p class="pb-8">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis, blanditiis iste corrupti necessitatibus optio
            distinctio dolorem, placeat quasi quas dolorum sapiente cumque accusamus architecto ducimus fuga id maiores,
            ullam aliquid.
          </p>
          <button
            class="ring dark:ring-0 ring-blue-300 rounded-lg py-3 px-8 dark:bg-teal-600 bg-black font-bold dark:text-white text-blue-50 shadow-2xl">Discover</button>
        </div>
      </div>

    </div>



    <div class="dark:bg-slate-950  w-full px-5 py-8 sm:px-20 textColor">
      <div v-for="(country, index) in countries" :key="index"
        :class="country.colorF, country.colorT, country.dColorF, country.dColorT"
        class="bg-gradient-to-br  rounded-2xl p-8 mx-5 mb-7 ">
        <h1 class="mb-4 font-bold text-3xl">{{ country.label }}</h1>
        <p class="font-bold dark:text-opacity-60 text-opacity-70 textColor mb-5 ">
          <span class="textColor ">Lorem ipsum dolor sit amet consectetur</span> adipisicing elit. Blanditiis, fuga eum
          quis animi delectus corporis similique ab totam voluptate ullam et sed quia laudantium odit omnis, beatae
          mollitia porro suscipit?
        </p>
        <h2 class="font-bold text-xl underline">Learn More.</h2>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
