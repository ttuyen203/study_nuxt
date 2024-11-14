<script setup>
import Header from "~/components/x-app/header.vue";
import Navbar_app from "~/components/x-app/navbar_app.vue";
import FlyMenu from "~/components/x-app/fly-menu.vue";

import comment from "../../assets/images/Comment Stroke Icon.svg";
import retweet from "../../assets/images/Retweet Stroke Icon.svg";
import heart from "../../assets/images/Heart Stroke Icon.svg";
import share from "../../assets/images/Share stroke icon.svg";

const isMenu = ref(false);

const handleClickMenu = () => {
  isMenu.value = !isMenu.value;
  console.log(isMenu.value);
};
</script>

<template>
  <div class="flex justify-center items-center px-5 bg-gray-500">
    <div class="w-[414px] relative overflow-hidden">
      <!-- Header -->
      <Header :handleClickMenu="handleClickMenu" />

      <!-- Content -->
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

      <!-- Overplay -->
      <div
        v-if="isMenu"
        class="absolute inset-0 bg-[#f3f5f7] opacity-50 z-40 mt-5"
        @click="handleClickMenu"
      ></div>

      <!-- Fly Menu -->
      <FlyMenu :isMenu="isMenu" />
    </div>
  </div>
</template>
