<script setup>
import Navbar_app from "~/components/x-app/navbar_app.vue";

import link from "../../../assets/images/Link Icon.svg";
import calendar from "../../../assets/images/Calendar Icon.svg";
</script>

<template>
  <div class="flex justify-center items-center px-5 bg-red-500">
    <div class="w-[414px] bg-white">
      <!-- Cover Image -->
      <div
        class="flex justify-between items-center w-[414px] bg-black px-5 py-4 h-36"
      >
        <p class="text-center w-full text-white">Cover Image</p>
      </div>

      <!-- Avatar and username -->
      <div class="relative">
        <div class="absolute -bottom-24 left-4">
          <img
            src="https://lumiere-a.akamaihd.net/v1/images/a_avatarpandorapedia_neytiri_16x9_1098_01_0e7d844a.jpeg?region=420%2C0%2C1080%2C1080"
            alt=""
            class="w-[68px] h-[68px] rounded-full border-4 border-white"
          />

          <div>
            <p class="text-[#141619] text-lg font-bold">To Tuyen</p>
            <p class="text-[#687684] text-base font-normal">@admin</p>
          </div>
        </div>
      </div>

      <!-- btn edit -->
      <div class="h-[105px]">
        <div class="flex justify-end px-5 py-2">
          <div
            class="border-[2px] border-[#4C9EEB] bg-white px-4 py-2 rounded-[100px] cursor-pointer"
          >
            <p class="w-full text-[#4C9EEB] text-center font-medium">
              Edit profile
            </p>
          </div>
        </div>
      </div>

      <div class="px-4">
        Digital Goodies Team - Web & Mobile IJI/UX development; Graphics;
        Illustrationss
      </div>

      <!--  -->
      <div class="flex items-center gap-5 px-4 mt-2">
        <div class="flex items-center gap-1.5">
          <img :src="link" alt="" />
          <p class="text-[#4C9EEB]">pixsellz.io</p>
        </div>

        <div class="flex items-center gap-1.5">
          <img :src="calendar" alt="" />
          <p class="text-[#687684]">Joined September 2018</p>
        </div>
      </div>

      <!-- Follower -->
      <div class="flex gap-5 mt-3 px-4">
        <div class="flex items-center gap-1 cursor-pointer">
          <p class="text-[#141619] font-medium">216</p>
          <p class="text-[#687684] font-normal">Following</p>
        </div>

        <div class="flex items-center gap-1 cursor-pointer">
          <p class="text-[#141619] font-medium">111</p>
          <p class="text-[#687684] font-normal">Followers</p>
        </div>
      </div>
      <!-- Navbar -->
      <Navbar_app />
    </div>
  </div>
</template>
