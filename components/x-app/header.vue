<script setup>
const props = defineProps({
  handleClickMenu: {
    type: Function,
  },
});

import Logo from "../../assets/images/Twitter Logo.svg";
import Feature from "../../assets/images/Feature stroke icon.svg";
</script>

<template>
  <div class="mt-5">
    <div
      class="flex justify-between items-center w-[414px] bg-white px-5 py-4 border-b border-[#bdc5cd] relative"
    >
      <!-- Image avatar -->
      <div class="cursor-pointer" @click="handleClickMenu">
        <img
          src="https://res.cloudinary.com/dymajn3ys/image/upload/v1731400068/study_nuxt/gy5jm0pctuhpp1c5x2ii.png"
          alt=""
          class="w-8 h-8 rounded-full"
        />
      </div>
      <!-- Logo -->
      <div class="cursor-pointer">
        <img :src="Logo" alt="" />
      </div>
      <!-- Feature icon -->
      <div>
        <img :src="Feature" alt="" />
      </div>
    </div>
  </div>
</template>
