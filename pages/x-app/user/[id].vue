<script setup>
import Navbar_app from "~/components/x-app/navbar_app.vue";

import link from "../../../assets/images/Link Icon.svg";
import calendar from "../../../assets/images/Calendar Icon.svg";
import comment from "../../assets/images/Comment Stroke Icon.svg";
import retweet from "../../assets/images/Retweet Stroke Icon.svg";
import heart from "../../assets/images/Heart Stroke Icon.svg";
import share from "../../assets/images/Share stroke icon.svg";
</script>

<template>
  <div class="flex justify-center items-center px-5 bg-gray-500">
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

      <!-- Tabs bar -->
      <div
        class="flex justify-between px-4 py-1 border-b border-[#bdc5cd] mt-2"
      >
        <NuxtLink
          exact-active-class="border-b border-[#4691d7] text-[#4691d7]"
          class="text-[#687684] font-medium"
          >Tweets</NuxtLink
        >
        <NuxtLink
          exact-active-class="border-b border-[#4691d7] text-[#4691d7]"
          class="text-[#687684] font-medium"
          >Tweets & replies</NuxtLink
        >
        <NuxtLink
          exact-active-class="border-b border-[#4691d7] text-[#4691d7]"
          class="text-[#687684] font-medium"
          >Media</NuxtLink
        >
        <NuxtLink
          exact-active-class="border-b border-[#4691d7] text-[#4691d7]"
          class="text-[#687684] font-medium"
          >Likes</NuxtLink
        >
      </div>

      <div class="flex flex-col relative pb-10">
        <!-- Content item -->
        <div
          class="flex gap-2 items-start w-full px-5 py-3 bg-white border-y border-[#ced5dc]"
        >
          <!-- Avatar -->
          <div class="w-1/6">
            <img
              src="https://res.cloudinary.com/dymajn3ys/image/upload/v1731400068/study_nuxt/gy5jm0pctuhpp1c5x2ii.png"
              alt=""
              class="w-14 h-14 rounded-full"
            />
          </div>
          <!-- Tweet -->
          <div class="w-5/6 flex flex-col">
            <!-- Infor user -->
            <p class="font-semibold">
              To Tuyen
              <span class="font-normal text-[#687684]"
                >@admin · 02/11/2024</span
              >
            </p>
            <!-- Post -->
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque,
              perspiciatis. Atque id, veniam vero laudantium molestiae libero
              natus odit ab voluptate voluptatum excepturi sint. Corrupti magni
              sunt sint eligendi quisquam?
            </p>
            <!-- Image Post -->
            <div class="mt-3">
              <img
                src="https://www.nasa.gov/wp-content/uploads/2023/07/iss069e018537-1.jpg?w=2048"
                alt=""
                class="rounded-xl"
              />
            </div>
            <!-- Interaction -->
            <div class="flex items-center gap-8 mt-3">
              <!-- Comment -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <div>
                  <img :src="comment" alt="" />
                </div>
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Retweet -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <div>
                  <img :src="retweet" alt="" />
                </div>
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Like -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <img :src="heart" alt="" />
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Share -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <img :src="share" alt="" />
              </div>
            </div>
          </div>
        </div>

        <!-- Content item -->
        <div
          class="flex gap-2 items-start w-full px-5 py-3 bg-white border-y border-[#ced5dc]"
        >
          <!-- Avatar -->
          <div class="w-1/6">
            <img
              src="https://res.cloudinary.com/dymajn3ys/image/upload/v1731400068/study_nuxt/gy5jm0pctuhpp1c5x2ii.png"
              alt=""
              class="w-14 h-14 rounded-full"
            />
          </div>
          <!-- Tweet -->
          <div class="w-5/6 flex flex-col">
            <!-- Infor user -->
            <p class="font-semibold">
              To Tuyen
              <span class="font-normal text-[#687684]"
                >@admin · 02/11/2024</span
              >
            </p>
            <!-- Post -->
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque,
              perspiciatis. Atque id, veniam vero laudantium molestiae libero
              natus odit ab voluptate voluptatum excepturi sint. Corrupti magni
              sunt sint eligendi quisquam?
            </p>
            <!-- Image Post -->
            <div class="mt-3">
              <img
                src="https://www.nasa.gov/wp-content/uploads/2023/07/iss069e018537-1.jpg?w=2048"
                alt=""
                class="rounded-xl"
              />
            </div>
            <!-- Interaction -->
            <div class="flex items-center gap-8 mt-3">
              <!-- Comment -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <div>
                  <img :src="comment" alt="" />
                </div>
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Retweet -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <div>
                  <img :src="retweet" alt="" />
                </div>
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Like -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <img :src="heart" alt="" />
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Share -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <img :src="share" alt="" />
              </div>
            </div>
          </div>
        </div>

        <!-- Content item -->
        <div
          class="flex gap-2 items-start w-full px-5 py-3 bg-white border-y border-[#ced5dc]"
        >
          <!-- Avatar -->
          <div class="w-1/6">
            <img
              src="https://res.cloudinary.com/dymajn3ys/image/upload/v1731400068/study_nuxt/gy5jm0pctuhpp1c5x2ii.png"
              alt=""
              class="w-14 h-14 rounded-full"
            />
          </div>
          <!-- Tweet -->
          <div class="w-5/6 flex flex-col">
            <!-- Infor user -->
            <p class="font-semibold">
              To Tuyen
              <span class="font-normal text-[#687684]"
                >@admin · 02/11/2024</span
              >
            </p>
            <!-- Post -->
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque,
              perspiciatis. Atque id, veniam vero laudantium molestiae libero
              natus odit ab voluptate voluptatum excepturi sint. Corrupti magni
              sunt sint eligendi quisquam?
            </p>
            <!-- Image Post -->
            <div class="mt-3">
              <img
                src="https://www.nasa.gov/wp-content/uploads/2023/07/iss069e018537-1.jpg?w=2048"
                alt=""
                class="rounded-xl"
              />
            </div>
            <!-- Interaction -->
            <div class="flex items-center gap-8 mt-3">
              <!-- Comment -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <div>
                  <img :src="comment" alt="" />
                </div>
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Retweet -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <div>
                  <img :src="retweet" alt="" />
                </div>
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Like -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <img :src="heart" alt="" />
                <!-- Number -->
                <p class="text-[#687684] text-sm">28</p>
              </div>

              <!-- Share -->
              <div class="flex gap-1 items-center cursor-pointer">
                <!-- icon -->
                <img :src="share" alt="" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Navbar -->
      <Navbar_app />
    </div>
  </div>
</template>
