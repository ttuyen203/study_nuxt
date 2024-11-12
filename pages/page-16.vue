<script setup>
import { ref } from "vue";
import img_6 from "../assets/images/image (6).png";
import img_7 from "../assets/images/image (7).png";
import img_8 from "../assets/images/image (8).png";
import img_9 from "../assets/images/image (9).png";
import img_10 from "../assets/images/image (10).png";
import img_11 from "../assets/images/image (11).png";
import video_banner from "../assets/images/video-banner.png";
import img_banner from "../assets/images/img-banner.png";

import logo_2 from "../assets/images/logo (2).png";

import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const isOpen = ref(false);

const isOpenStore = ref(false);
const isOpenCompany = ref(false);

const changeImage = (src) => {
  document.getElementById("mainImage").src = src;
};
</script>

<template>
  <div class="flex justify-center items-center">
    <div class="bg-white w-[390px] relative">
      <!-- frame btn change language -->
      <div class="absolute right-0">
        <div class="flex-col pt-4 px-6">
          <div
            @click="isOpen = !isOpen"
            class="flex items-center gap-1 py-1.5 px-3 bg-white rounded-[100px] mb-[7px]"
          >
            <div>
              <svg
                width="17"
                height="17"
                viewBox="0 0 17 17"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g id="Software/world">
                  <g id="Vector">
                    <path
                      d="M8.00667 0C3.58667 0 0 3.58667 0 8.00667C0 12.4267 3.58667 16.0133 8.00667 16.0133C12.4267 16.0133 16.0133 12.4267 16.0133 8.00667C16.0133 3.58667 12.4267 0 8.00667 0ZM2.30667 11.4533C1.85333 10.7067 1.54 9.86667 1.41333 8.96667C1.41333 8.95333 1.41333 8.94667 1.41333 8.93333C1.37333 8.62667 1.34667 8.32 1.34667 8.00667C1.34667 7.76 1.36 7.51333 1.38667 7.27333C2.27333 7.08 3.32667 6.96 4.06667 7.09333C4.47333 7.16667 4.66 7.29333 4.73333 7.39333C4.78 7.46 4.87333 7.64667 4.71333 8.12667C4.46667 8.87333 4.29333 9.41333 4.18667 9.82C4.08667 10.2133 4.02667 10.5533 4.06 10.8667C4.1 11.2133 4.24 11.4533 4.36 11.6467C4.38 11.68 4.40667 11.72 4.42667 11.7533C4.52667 11.9067 4.62667 12.06 4.74667 12.3C5.02667 12.86 5 13.4667 4.90667 13.9C4.64667 13.76 4.4 13.6067 4.16 13.44C4.14667 13.4267 4.13333 13.42 4.11333 13.4067C3.89333 13.2533 3.69333 13.08 3.49333 12.9C3.47333 12.88 3.45333 12.86 3.42667 12.84C3.01333 12.4467 2.65333 12.0067 2.34667 11.52C2.33333 11.4933 2.31333 11.4667 2.3 11.4467L2.30667 11.4533ZM8.55333 12.2133C9.26 13.5533 9.14667 14.06 9.06 14.2133C8.93333 14.44 8.54 14.5933 7.87333 14.6533C7.6 14.6533 7.33333 14.6333 7.06667 14.6C7.05333 14.6 7.04667 14.6 7.03333 14.6C6.72667 14.5533 6.43333 14.4933 6.14667 14.4067C6.34 13.72 6.43333 12.6933 5.93333 11.7067C5.78 11.3933 5.63333 11.1733 5.53333 11.0133C5.51333 10.98 5.49333 10.9533 5.48 10.9333C5.38667 10.78 5.38 10.7533 5.38 10.72C5.37333 10.66 5.38 10.52 5.47333 10.1533C5.56667 9.8 5.72667 9.3 5.97333 8.54667C6.21333 7.82667 6.2 7.14667 5.80667 6.60667C5.44 6.1 4.84667 5.88 4.3 5.78C3.5 5.63333 2.53333 5.71333 1.69333 5.85333C1.69333 5.85333 1.69333 5.84667 1.69333 5.84C1.76667 5.62 1.86 5.4 1.96 5.19333C1.97333 5.16667 1.98667 5.14 2 5.11333C2.09333 4.92 2.19333 4.73333 2.30667 4.55333C2.32667 4.52667 2.34 4.49333 2.36 4.46667C2.47333 4.28 2.6 4.1 2.73333 3.93333C2.74667 3.91333 2.76 3.9 2.77333 3.88C2.92 3.69333 3.08 3.50667 3.25333 3.34C3.32667 3.35333 3.40667 3.34667 3.48667 3.32667C3.93333 3.22667 4.7 3.13333 5.50667 3.19333C6.32 3.25333 7.08 3.45333 7.59333 3.86667C7.90667 4.12 8.14 4.4 8.39333 4.70667C8.42 4.74 8.45333 4.78 8.48 4.81333C8.75333 5.14 9.09333 5.54667 9.6 5.78C10.1333 6.03333 10.7533 6.05333 11.5 5.86667C12.14 5.7 12.9133 5.37333 13.8733 4.84667C14 5.08 14.1133 5.32 14.2067 5.57333C14.2067 5.58 14.2067 5.58667 14.2133 5.59333C14.3067 5.83333 14.3867 6.07333 14.4467 6.32667C14.4467 6.34667 14.4533 6.36667 14.46 6.38667C14.5933 6.90667 14.66 7.45333 14.66 8.02C14.66 8.03333 14.66 8.04 14.66 8.04667C14.66 9 14.4467 9.91333 14.08 10.7333C13.5467 8.58667 12.5667 7.82 11.7667 7.58C10.8 7.28667 9.73333 7.67333 8.98667 8.58C8.10667 9.64667 7.93333 11.08 8.54 12.2267L8.55333 12.2133ZM10.24 1.72C10.44 1.79333 10.64 1.87333 10.8333 1.96667C10.86 1.98 10.8933 1.99333 10.92 2.00667C11.1 2.09333 11.28 2.19333 11.4533 2.3C11.4867 2.32 11.5133 2.34 11.5467 2.35333C11.72 2.46 11.8867 2.58 12.0467 2.7C12.0733 2.72 12.0933 2.73333 12.12 2.75333C12.2933 2.89333 12.4667 3.04 12.6267 3.19333C12.6267 3.19333 12.64 3.2 12.64 3.20667C12.8133 3.37333 12.9733 3.54667 13.1267 3.72667C12.2667 4.18667 11.64 4.44 11.1733 4.56C10.62 4.7 10.34 4.64 10.1667 4.56C9.96 4.46667 9.78667 4.28667 9.50667 3.94667C9.48 3.91333 9.45333 3.88 9.42 3.84C9.17333 3.54 8.85333 3.15333 8.42667 2.80667C7.60667 2.15333 6.53333 1.91333 5.6 1.84667C5.55333 1.84667 5.5 1.84667 5.45333 1.84C6.24 1.51333 7.10667 1.33333 8.01333 1.33333C8.78 1.33333 9.51333 1.46 10.1933 1.7C10.2133 1.7 10.2267 1.71333 10.2467 1.72H10.24ZM10.44 14.2067C10.5333 13.52 10.3 12.6667 9.73333 11.5867C9.3 10.7667 9.62667 9.9 10.0333 9.40667C10.3467 9.02667 10.8733 8.67333 11.4 8.83333C12.2 9.07333 12.8 10.3933 13.04 12.3667C12.34 13.1733 11.4533 13.8067 10.4467 14.2L10.44 14.2067Z"
                      fill="#3A424E"
                    />
                    <path
                      d="M8.00667 0C3.58667 0 0 3.58667 0 8.00667C0 12.4267 3.58667 16.0133 8.00667 16.0133C12.4267 16.0133 16.0133 12.4267 16.0133 8.00667C16.0133 3.58667 12.4267 0 8.00667 0ZM2.30667 11.4533C1.85333 10.7067 1.54 9.86667 1.41333 8.96667C1.41333 8.95333 1.41333 8.94667 1.41333 8.93333C1.37333 8.62667 1.34667 8.32 1.34667 8.00667C1.34667 7.76 1.36 7.51333 1.38667 7.27333C2.27333 7.08 3.32667 6.96 4.06667 7.09333C4.47333 7.16667 4.66 7.29333 4.73333 7.39333C4.78 7.46 4.87333 7.64667 4.71333 8.12667C4.46667 8.87333 4.29333 9.41333 4.18667 9.82C4.08667 10.2133 4.02667 10.5533 4.06 10.8667C4.1 11.2133 4.24 11.4533 4.36 11.6467C4.38 11.68 4.40667 11.72 4.42667 11.7533C4.52667 11.9067 4.62667 12.06 4.74667 12.3C5.02667 12.86 5 13.4667 4.90667 13.9C4.64667 13.76 4.4 13.6067 4.16 13.44C4.14667 13.4267 4.13333 13.42 4.11333 13.4067C3.89333 13.2533 3.69333 13.08 3.49333 12.9C3.47333 12.88 3.45333 12.86 3.42667 12.84C3.01333 12.4467 2.65333 12.0067 2.34667 11.52C2.33333 11.4933 2.31333 11.4667 2.3 11.4467L2.30667 11.4533ZM8.55333 12.2133C9.26 13.5533 9.14667 14.06 9.06 14.2133C8.93333 14.44 8.54 14.5933 7.87333 14.6533C7.6 14.6533 7.33333 14.6333 7.06667 14.6C7.05333 14.6 7.04667 14.6 7.03333 14.6C6.72667 14.5533 6.43333 14.4933 6.14667 14.4067C6.34 13.72 6.43333 12.6933 5.93333 11.7067C5.78 11.3933 5.63333 11.1733 5.53333 11.0133C5.51333 10.98 5.49333 10.9533 5.48 10.9333C5.38667 10.78 5.38 10.7533 5.38 10.72C5.37333 10.66 5.38 10.52 5.47333 10.1533C5.56667 9.8 5.72667 9.3 5.97333 8.54667C6.21333 7.82667 6.2 7.14667 5.80667 6.60667C5.44 6.1 4.84667 5.88 4.3 5.78C3.5 5.63333 2.53333 5.71333 1.69333 5.85333C1.69333 5.85333 1.69333 5.84667 1.69333 5.84C1.76667 5.62 1.86 5.4 1.96 5.19333C1.97333 5.16667 1.98667 5.14 2 5.11333C2.09333 4.92 2.19333 4.73333 2.30667 4.55333C2.32667 4.52667 2.34 4.49333 2.36 4.46667C2.47333 4.28 2.6 4.1 2.73333 3.93333C2.74667 3.91333 2.76 3.9 2.77333 3.88C2.92 3.69333 3.08 3.50667 3.25333 3.34C3.32667 3.35333 3.40667 3.34667 3.48667 3.32667C3.93333 3.22667 4.7 3.13333 5.50667 3.19333C6.32 3.25333 7.08 3.45333 7.59333 3.86667C7.90667 4.12 8.14 4.4 8.39333 4.70667C8.42 4.74 8.45333 4.78 8.48 4.81333C8.75333 5.14 9.09333 5.54667 9.6 5.78C10.1333 6.03333 10.7533 6.05333 11.5 5.86667C12.14 5.7 12.9133 5.37333 13.8733 4.84667C14 5.08 14.1133 5.32 14.2067 5.57333C14.2067 5.58 14.2067 5.58667 14.2133 5.59333C14.3067 5.83333 14.3867 6.07333 14.4467 6.32667C14.4467 6.34667 14.4533 6.36667 14.46 6.38667C14.5933 6.90667 14.66 7.45333 14.66 8.02C14.66 8.03333 14.66 8.04 14.66 8.04667C14.66 9 14.4467 9.91333 14.08 10.7333C13.5467 8.58667 12.5667 7.82 11.7667 7.58C10.8 7.28667 9.73333 7.67333 8.98667 8.58C8.10667 9.64667 7.93333 11.08 8.54 12.2267L8.55333 12.2133ZM10.24 1.72C10.44 1.79333 10.64 1.87333 10.8333 1.96667C10.86 1.98 10.8933 1.99333 10.92 2.00667C11.1 2.09333 11.28 2.19333 11.4533 2.3C11.4867 2.32 11.5133 2.34 11.5467 2.35333C11.72 2.46 11.8867 2.58 12.0467 2.7C12.0733 2.72 12.0933 2.73333 12.12 2.75333C12.2933 2.89333 12.4667 3.04 12.6267 3.19333C12.6267 3.19333 12.64 3.2 12.64 3.20667C12.8133 3.37333 12.9733 3.54667 13.1267 3.72667C12.2667 4.18667 11.64 4.44 11.1733 4.56C10.62 4.7 10.34 4.64 10.1667 4.56C9.96 4.46667 9.78667 4.28667 9.50667 3.94667C9.48 3.91333 9.45333 3.88 9.42 3.84C9.17333 3.54 8.85333 3.15333 8.42667 2.80667C7.60667 2.15333 6.53333 1.91333 5.6 1.84667C5.55333 1.84667 5.5 1.84667 5.45333 1.84C6.24 1.51333 7.10667 1.33333 8.01333 1.33333C8.78 1.33333 9.51333 1.46 10.1933 1.7C10.2133 1.7 10.2267 1.71333 10.2467 1.72H10.24ZM10.44 14.2067C10.5333 13.52 10.3 12.6667 9.73333 11.5867C9.3 10.7667 9.62667 9.9 10.0333 9.40667C10.3467 9.02667 10.8733 8.67333 11.4 8.83333C12.2 9.07333 12.8 10.3933 13.04 12.3667C12.34 13.1733 11.4533 13.8067 10.4467 14.2L10.44 14.2067Z"
                      fill="black"
                      fill-opacity="0.2"
                    />
                  </g>
                </g>
              </svg>
            </div>
            <p class="text-[#2E353E] text-sm font-semibold cursor-pointer">
              ENG
            </p>
            <div>
              <svg
                width="16"
                height="16"
                viewBox="0 0 16 16"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g id="Arrows/chevron/down">
                  <g id="Icon (Stroke)">
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M3.5286 6.19526C3.78895 5.93491 4.21106 5.93491 4.47141 6.19526L8 9.72386L11.5286 6.19526C11.7889 5.93491 12.2111 5.93491 12.4714 6.19526C12.7318 6.45561 12.7318 6.87772 12.4714 7.13807L8.94281 10.6667C8.42211 11.1874 7.57789 11.1874 7.05719 10.6667L3.5286 7.13807C3.26825 6.87772 3.26825 6.45561 3.5286 6.19526Z"
                      fill="#3A424E"
                    />
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M3.5286 6.19526C3.78895 5.93491 4.21106 5.93491 4.47141 6.19526L8 9.72386L11.5286 6.19526C11.7889 5.93491 12.2111 5.93491 12.4714 6.19526C12.7318 6.45561 12.7318 6.87772 12.4714 7.13807L8.94281 10.6667C8.42211 11.1874 7.57789 11.1874 7.05719 10.6667L3.5286 7.13807C3.26825 6.87772 3.26825 6.45561 3.5286 6.19526Z"
                      fill="black"
                      fill-opacity="0.2"
                    />
                  </g>
                </g>
              </svg>
            </div>
          </div>
          <!-- box content change language -->
          <div
            v-if="isOpen"
            class="border shadow-gray-400 shadow-inner transition-all duration-200 ease-in-out"
          >
            <div
              class="text-[#2E353E] text-sm font-semibold bg-white text-center py-2 hover:bg-[#e1ecdc] cursor-pointer"
            >
              ENG
            </div>
            <div
              class="text-[#2E353E] text-sm font-semibold bg-white text-center py-2 hover:bg-[#e1ecdc] cursor-pointer"
            >
              VIE
            </div>
          </div>
        </div>
      </div>

      <!-- Frame Image -->
      <div class="flex justify-center items-center px-2 pt-[55px] pb-4">
        <div class="bg-[#FFF7D8] p-4 rounded-[20px]">
          <!-- Main Image -->
          <div>
            <img
              :src="img_6"
              alt=""
              class="rounded-2xl w-[342px] h-[342px]"
              id="mainImage"
            />
          </div>
          <!-- List image -->
          <div class="mt-2.5 flex justify-between">
            <!-- image item -->
            <div>
              <img
                :src="img_6"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(img_6)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="img_7"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(img_7)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="img_8"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(img_8)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="img_9"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(img_9)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="img_10"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(img_10)"
              />
            </div>
          </div>
        </div>
      </div>

      <!-- Text -->
      <div class="flex justify-center items-center p-4 bg-[#7D9BD1]">
        <p class="font-normal text-white">
          Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse
          molestie consequat, vel illum dolore eu feugiat nulla facilisis at
          vero
        </p>
      </div>

      <!-- Infor Product -->
      <div class="flex flex-col gap-4 items-center px-2 py-4">
        <!-- Name, price, size -->
        <div class="p-4 bg-[#DFF4FF] rounded-[20px] w-full">
          <div class="mb-4 flex flex-col gap-1">
            <p
              class="text-[#1E306E] text-xl font-bold leading-[25px] tracking-wide"
            >
              Chicco Kwik.One
            </p>
            <p
              class="text-[#1E306E] text-xl font-bold leading-[25px] tracking-wide"
            >
              $20
            </p>
          </div>

          <div class="flex gap-4 items-center">
            <p
              class="text-[#2E353E] font-bold leading-[21px] tracking-[0.02em]"
            >
              Size
            </p>
            <div
              class="flex justify-center items-center py-2 px-6 bg-white rounded-[100px] cursor-pointer"
            >
              X
            </div>
            <div
              class="flex justify-center items-center py-2 px-6 bg-white rounded-[100px] cursor-pointer"
            >
              XS
            </div>
          </div>
        </div>

        <!-- Desc -->
        <div
          class="flex flex-col gap-4 items-center py-6 px-4 bg-[#F4F6F8] w-full rounded-[20px]"
        >
          <!-- Nav -->
          <div
            class="flex gap-2 justify-center items-center border-b border-white px-4"
          >
            <div
              class="text-[#1E306E] font-bold leading-[21px] tracking-[0.02em] border-b-2 border-[#1E306E] px-6 pb-4 cursor-pointer"
            >
              Description
            </div>
            <div>
              <p
                class="text-[#626F82] leading-[21px] tracking-[0.02em] font-bold px-6 pb-4 cursor-pointer"
              >
                Information
              </p>
            </div>
          </div>

          <!-- Desc content -->
          <div>
            <p
              class="text-[#2E353E] font-normal leading-[21px] tracking-[0.02em] text-base"
            >
              Meet the new cute and full of functions baby carriage for
              newborns! Small four-wheeled carriage often with a folding top for
              pushing a baby around in – called also baby buggy – has a bunch of
              characteristics, such as: Wheels:6*7″ EVA Suspension on front and
              rear wheels One-step brake One hand folding with second lock
              Removable Front&Up Tray Three positions for seat
            </p>
          </div>
        </div>

        <!-- Video banner -->
        <div class="relative">
          <img :src="video_banner" alt="" class="rounded-[20px]" />
          <div
            class="absolute left-[157px] bottom-[75.19px] p-2.5 flex justify-center items-center w-[60px] h-[60px] gap-2.5 border border-[#ffffff33] bg-[#ffffff33] rounded-full cursor-pointer"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="25"
              viewBox="0 0 24 25"
              fill="none"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M6 6.25357C6 3.76455 8.85628 2.35812 10.8291 3.8757L18.5489 9.81397C20.11 11.0149 20.11 13.3688 18.5489 14.5697L10.8291 20.508C8.85628 22.0256 6 20.6191 6 18.1301V6.25357Z"
                fill="white"
              />
            </svg>
          </div>
        </div>

        <!-- Image banner -->
        <img :src="img_banner" alt="" class="rounded-[20px]" />

        <!-- Related products -->
        <div class="flex flex-col py-2">
          <!-- Related products title -->
          <div class="flex justify-center items-center gap-2">
            <p
              class="text-[#1E306E] text-2xl font-bold leading-[30px] tracking-[0.48px]"
            >
              Related products
            </p>
          </div>
          <!-- Related products content -->
          <div class="flex items-start gap-4">
            <Swiper
              :slidesPerView="'auto'"
              :spaceBetween="30"
              :pagination="{
                clickable: true,
              }"
              :modules="modules"
            >
              <swiper-slide>
                <div>
                  <img :src="img_11" alt="" />
                  <div class="flex flex-col items-center gap-1">
                    <p
                      class="text-[#2e353e] font-bold text-base leading-[21px] tracking-[0.32px]"
                    >
                      Chicco Kwik.One
                    </p>
                    <p
                      class="text-[#1E306E] text-xl font-bold leading-[26.6px] tracking-[0.4px]"
                    >
                      $50.00 USD
                    </p>
                  </div>
                </div>
              </swiper-slide>
              <swiper-slide>
                <div>
                  <img :src="img_11" alt="" />
                  <div class="flex flex-col items-center gap-1">
                    <p
                      class="text-[#2e353e] font-bold text-base leading-[21px] tracking-[0.32px]"
                    >
                      Chicco Kwik.One
                    </p>
                    <p
                      class="text-[#1E306E] text-xl font-bold leading-[26.6px] tracking-[0.4px]"
                    >
                      $50.00 USD
                    </p>
                  </div>
                </div>
              </swiper-slide>
            </Swiper>
          </div>
        </div>
      </div>

      <!-- Infor store and company -->
      <div
        class="flex p-4 justify-center items-center flex-col gap-2.5 bg-[#7D9BD1]"
      >
        <!-- Store -->
        <div
          class="flex py-4 justify-between items-center w-full"
          @click="isOpenStore = !isOpenStore"
        >
          <p
            class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
          >
            Store
          </p>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M10.5858 7.99985C11.3668 7.2188 12.6332 7.2188 13.4142 7.99985L18.7071 13.2927C19.0976 13.6833 19.0976 14.3164 18.7071 14.707C18.3166 15.0975 17.6834 15.0975 17.2929 14.707L12 9.41406L6.70711 14.707C6.31658 15.0975 5.68342 15.0975 5.29289 14.707C4.90237 14.3164 4.90237 13.6833 5.29289 13.2927L10.5858 7.99985Z"
              fill="white"
            />
          </svg>
        </div>
        <!-- Collapse item store-->
        <div class="flex flex-col gap-4 w-full pb-5" v-if="isOpenStore">
          <!-- QR and name -->
          <div class="flex gap-4 items-center">
            <img
              :src="logo_2"
              alt=""
              class="w-[52px] h-[52px] rounded-[10px] border border-[#E0E2E6]"
            />
            <div class="flex flex-col gap-1 flex-1">
              <p
                class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
              >
                SofaKart
              </p>
              <p
                class="text-white text-base font-semibold leading-[20px] tracking-[0.32px]"
              >
                Business owned
              </p>
            </div>
          </div>

          <!-- Phone number and address -->
          <div class="flex flex-col gap-3">
            <!-- Phone number -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7.63039 0.833984H12.3571C12.7947 0.833984 13.1699 0.833984 13.4825 0.858979C13.8076 0.883973 14.1452 0.946459 14.4578 1.10892C14.933 1.34637 15.3081 1.73378 15.5457 2.19617C15.7083 2.5086 15.7708 2.83353 15.7958 3.17095C15.8208 3.48338 15.8208 3.8583 15.8208 4.2957V15.6931C15.8208 16.1305 15.8208 16.5054 15.7958 16.8179C15.7708 17.1428 15.7083 17.4802 15.5457 17.7926C15.3081 18.2675 14.9205 18.6424 14.4578 18.8799C14.1452 19.0423 13.8201 19.1048 13.4825 19.1298C13.1699 19.1548 12.7947 19.1548 12.3571 19.1548H7.63039C7.19274 19.1548 6.8176 19.1548 6.50499 19.1298C6.17988 19.1048 5.84225 19.0423 5.52964 18.8799C5.05447 18.6424 4.67934 18.255 4.44175 17.7926C4.2792 17.4802 4.21667 17.1553 4.19167 16.8179C4.16666 16.5179 4.16666 16.1305 4.16666 15.6931V4.2957C4.16666 3.8583 4.16666 3.48338 4.19167 3.17095C4.21667 2.84603 4.2792 2.5086 4.44175 2.19617C4.67934 1.72128 5.06698 1.34637 5.52964 1.10892C5.84225 0.946459 6.17988 0.883973 6.50499 0.858979C6.8176 0.833984 7.19274 0.833984 7.63039 0.833984ZM8.33064 4.17073C8.33064 3.70833 8.70578 3.33342 9.16844 3.33342H10.8315C11.2942 3.33342 11.6693 3.70833 11.6693 4.17073C11.6693 4.63312 11.2942 5.00804 10.8315 5.00804H9.16844C8.70578 5.00804 8.33064 4.63312 8.33064 4.17073Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                0988 777 777
              </p>
            </div>
            <!-- Address -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M2.5 8.33228C2.5 4.19572 5.8625 0.833984 10 0.833984C14.1375 0.833984 17.5 4.19572 17.5 8.33228C17.5 9.41953 17.1375 10.6318 16.625 11.7815C16.1 12.9562 15.4 14.131 14.6375 15.1932C13.8875 16.243 13.0625 17.1928 12.3125 17.8926C11.9375 18.2425 11.5625 18.5425 11.2 18.7549C10.8625 18.9549 10.4375 19.1548 10 19.1548C9.5625 19.1548 9.1375 18.9549 8.8 18.7549C8.4375 18.5425 8.0625 18.2425 7.6875 17.8926C6.9375 17.1928 6.1125 16.243 5.3625 15.1932C4.6125 14.1435 3.9 12.9562 3.375 11.7815C2.8625 10.6193 2.5 9.41953 2.5 8.33228ZM5.8375 8.33228C5.8375 6.0328 7.7 4.17073 10 4.17073C12.3 4.17073 14.1625 6.0328 14.1625 8.33228C14.1625 10.6318 12.3 12.4938 10 12.4938C7.7 12.4938 5.8375 10.6318 5.8375 8.33228Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                Hanoi, Vietnam
              </p>
            </div>
          </div>
        </div>

        <div class="flex flex-col gap-4 w-full pb-5" v-if="isOpenStore">
          <!-- QR and name -->
          <div class="flex gap-4 items-center">
            <img
              :src="logo_2"
              alt=""
              class="w-[52px] h-[52px] rounded-[10px] border border-[#E0E2E6]"
            />
            <div class="flex flex-col gap-1 flex-1">
              <p
                class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
              >
                SofaKart
              </p>
              <p
                class="text-white text-base font-semibold leading-[20px] tracking-[0.32px]"
              >
                Business owned
              </p>
            </div>
          </div>

          <!-- Phone number and address -->
          <div class="flex flex-col gap-3">
            <!-- Phone number -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7.63039 0.833984H12.3571C12.7947 0.833984 13.1699 0.833984 13.4825 0.858979C13.8076 0.883973 14.1452 0.946459 14.4578 1.10892C14.933 1.34637 15.3081 1.73378 15.5457 2.19617C15.7083 2.5086 15.7708 2.83353 15.7958 3.17095C15.8208 3.48338 15.8208 3.8583 15.8208 4.2957V15.6931C15.8208 16.1305 15.8208 16.5054 15.7958 16.8179C15.7708 17.1428 15.7083 17.4802 15.5457 17.7926C15.3081 18.2675 14.9205 18.6424 14.4578 18.8799C14.1452 19.0423 13.8201 19.1048 13.4825 19.1298C13.1699 19.1548 12.7947 19.1548 12.3571 19.1548H7.63039C7.19274 19.1548 6.8176 19.1548 6.50499 19.1298C6.17988 19.1048 5.84225 19.0423 5.52964 18.8799C5.05447 18.6424 4.67934 18.255 4.44175 17.7926C4.2792 17.4802 4.21667 17.1553 4.19167 16.8179C4.16666 16.5179 4.16666 16.1305 4.16666 15.6931V4.2957C4.16666 3.8583 4.16666 3.48338 4.19167 3.17095C4.21667 2.84603 4.2792 2.5086 4.44175 2.19617C4.67934 1.72128 5.06698 1.34637 5.52964 1.10892C5.84225 0.946459 6.17988 0.883973 6.50499 0.858979C6.8176 0.833984 7.19274 0.833984 7.63039 0.833984ZM8.33064 4.17073C8.33064 3.70833 8.70578 3.33342 9.16844 3.33342H10.8315C11.2942 3.33342 11.6693 3.70833 11.6693 4.17073C11.6693 4.63312 11.2942 5.00804 10.8315 5.00804H9.16844C8.70578 5.00804 8.33064 4.63312 8.33064 4.17073Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                0988 777 777
              </p>
            </div>
            <!-- Address -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M2.5 8.33228C2.5 4.19572 5.8625 0.833984 10 0.833984C14.1375 0.833984 17.5 4.19572 17.5 8.33228C17.5 9.41953 17.1375 10.6318 16.625 11.7815C16.1 12.9562 15.4 14.131 14.6375 15.1932C13.8875 16.243 13.0625 17.1928 12.3125 17.8926C11.9375 18.2425 11.5625 18.5425 11.2 18.7549C10.8625 18.9549 10.4375 19.1548 10 19.1548C9.5625 19.1548 9.1375 18.9549 8.8 18.7549C8.4375 18.5425 8.0625 18.2425 7.6875 17.8926C6.9375 17.1928 6.1125 16.243 5.3625 15.1932C4.6125 14.1435 3.9 12.9562 3.375 11.7815C2.8625 10.6193 2.5 9.41953 2.5 8.33228ZM5.8375 8.33228C5.8375 6.0328 7.7 4.17073 10 4.17073C12.3 4.17073 14.1625 6.0328 14.1625 8.33228C14.1625 10.6318 12.3 12.4938 10 12.4938C7.7 12.4938 5.8375 10.6318 5.8375 8.33228Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                Hanoi, Vietnam
              </p>
            </div>
          </div>
        </div>

        <!-- Company -->
        <div
          class="flex py-4 justify-between items-center w-full"
          @click="isOpenCompany = !isOpenCompany"
        >
          <p
            class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
          >
            Company
          </p>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M10.5858 7.99985C11.3668 7.2188 12.6332 7.2188 13.4142 7.99985L18.7071 13.2927C19.0976 13.6833 19.0976 14.3164 18.7071 14.707C18.3166 15.0975 17.6834 15.0975 17.2929 14.707L12 9.41406L6.70711 14.707C6.31658 15.0975 5.68342 15.0975 5.29289 14.707C4.90237 14.3164 4.90237 13.6833 5.29289 13.2927L10.5858 7.99985Z"
              fill="white"
            />
          </svg>
        </div>
        <!-- Collapse item company-->
        <div class="flex flex-col gap-4 w-full pb-5" v-if="isOpenCompany">
          <!-- QR and name -->
          <div class="flex gap-4 items-center">
            <img
              :src="logo_2"
              alt=""
              class="w-[52px] h-[52px] rounded-[10px] border border-[#E0E2E6]"
            />
            <div class="flex flex-col gap-1 flex-1">
              <p
                class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
              >
                SofaKart
              </p>
              <p
                class="text-white text-base font-semibold leading-[20px] tracking-[0.32px]"
              >
                Business owned
              </p>
            </div>
          </div>

          <!-- Phone number and address -->
          <div class="flex flex-col gap-3">
            <!-- Phone number -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7.63039 0.833984H12.3571C12.7947 0.833984 13.1699 0.833984 13.4825 0.858979C13.8076 0.883973 14.1452 0.946459 14.4578 1.10892C14.933 1.34637 15.3081 1.73378 15.5457 2.19617C15.7083 2.5086 15.7708 2.83353 15.7958 3.17095C15.8208 3.48338 15.8208 3.8583 15.8208 4.2957V15.6931C15.8208 16.1305 15.8208 16.5054 15.7958 16.8179C15.7708 17.1428 15.7083 17.4802 15.5457 17.7926C15.3081 18.2675 14.9205 18.6424 14.4578 18.8799C14.1452 19.0423 13.8201 19.1048 13.4825 19.1298C13.1699 19.1548 12.7947 19.1548 12.3571 19.1548H7.63039C7.19274 19.1548 6.8176 19.1548 6.50499 19.1298C6.17988 19.1048 5.84225 19.0423 5.52964 18.8799C5.05447 18.6424 4.67934 18.255 4.44175 17.7926C4.2792 17.4802 4.21667 17.1553 4.19167 16.8179C4.16666 16.5179 4.16666 16.1305 4.16666 15.6931V4.2957C4.16666 3.8583 4.16666 3.48338 4.19167 3.17095C4.21667 2.84603 4.2792 2.5086 4.44175 2.19617C4.67934 1.72128 5.06698 1.34637 5.52964 1.10892C5.84225 0.946459 6.17988 0.883973 6.50499 0.858979C6.8176 0.833984 7.19274 0.833984 7.63039 0.833984ZM8.33064 4.17073C8.33064 3.70833 8.70578 3.33342 9.16844 3.33342H10.8315C11.2942 3.33342 11.6693 3.70833 11.6693 4.17073C11.6693 4.63312 11.2942 5.00804 10.8315 5.00804H9.16844C8.70578 5.00804 8.33064 4.63312 8.33064 4.17073Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                0988 777 777
              </p>
            </div>
            <!-- Address -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M2.5 8.33228C2.5 4.19572 5.8625 0.833984 10 0.833984C14.1375 0.833984 17.5 4.19572 17.5 8.33228C17.5 9.41953 17.1375 10.6318 16.625 11.7815C16.1 12.9562 15.4 14.131 14.6375 15.1932C13.8875 16.243 13.0625 17.1928 12.3125 17.8926C11.9375 18.2425 11.5625 18.5425 11.2 18.7549C10.8625 18.9549 10.4375 19.1548 10 19.1548C9.5625 19.1548 9.1375 18.9549 8.8 18.7549C8.4375 18.5425 8.0625 18.2425 7.6875 17.8926C6.9375 17.1928 6.1125 16.243 5.3625 15.1932C4.6125 14.1435 3.9 12.9562 3.375 11.7815C2.8625 10.6193 2.5 9.41953 2.5 8.33228ZM5.8375 8.33228C5.8375 6.0328 7.7 4.17073 10 4.17073C12.3 4.17073 14.1625 6.0328 14.1625 8.33228C14.1625 10.6318 12.3 12.4938 10 12.4938C7.7 12.4938 5.8375 10.6318 5.8375 8.33228Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                Hanoi, Vietnam
              </p>
            </div>
          </div>
        </div>

        <div class="flex flex-col gap-4 w-full pb-5" v-if="isOpenCompany">
          <!-- QR and name -->
          <div class="flex gap-4 items-center">
            <img
              :src="logo_2"
              alt=""
              class="w-[52px] h-[52px] rounded-[10px] border border-[#E0E2E6]"
            />
            <div class="flex flex-col gap-1 flex-1">
              <p
                class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
              >
                SofaKart
              </p>
              <p
                class="text-white text-base font-semibold leading-[20px] tracking-[0.32px]"
              >
                Business owned
              </p>
            </div>
          </div>

          <!-- Phone number and address -->
          <div class="flex flex-col gap-3">
            <!-- Phone number -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7.63039 0.833984H12.3571C12.7947 0.833984 13.1699 0.833984 13.4825 0.858979C13.8076 0.883973 14.1452 0.946459 14.4578 1.10892C14.933 1.34637 15.3081 1.73378 15.5457 2.19617C15.7083 2.5086 15.7708 2.83353 15.7958 3.17095C15.8208 3.48338 15.8208 3.8583 15.8208 4.2957V15.6931C15.8208 16.1305 15.8208 16.5054 15.7958 16.8179C15.7708 17.1428 15.7083 17.4802 15.5457 17.7926C15.3081 18.2675 14.9205 18.6424 14.4578 18.8799C14.1452 19.0423 13.8201 19.1048 13.4825 19.1298C13.1699 19.1548 12.7947 19.1548 12.3571 19.1548H7.63039C7.19274 19.1548 6.8176 19.1548 6.50499 19.1298C6.17988 19.1048 5.84225 19.0423 5.52964 18.8799C5.05447 18.6424 4.67934 18.255 4.44175 17.7926C4.2792 17.4802 4.21667 17.1553 4.19167 16.8179C4.16666 16.5179 4.16666 16.1305 4.16666 15.6931V4.2957C4.16666 3.8583 4.16666 3.48338 4.19167 3.17095C4.21667 2.84603 4.2792 2.5086 4.44175 2.19617C4.67934 1.72128 5.06698 1.34637 5.52964 1.10892C5.84225 0.946459 6.17988 0.883973 6.50499 0.858979C6.8176 0.833984 7.19274 0.833984 7.63039 0.833984ZM8.33064 4.17073C8.33064 3.70833 8.70578 3.33342 9.16844 3.33342H10.8315C11.2942 3.33342 11.6693 3.70833 11.6693 4.17073C11.6693 4.63312 11.2942 5.00804 10.8315 5.00804H9.16844C8.70578 5.00804 8.33064 4.63312 8.33064 4.17073Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                0988 777 777
              </p>
            </div>
            <!-- Address -->
            <div class="flex items-center gap-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <g opacity="0.5">
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M2.5 8.33228C2.5 4.19572 5.8625 0.833984 10 0.833984C14.1375 0.833984 17.5 4.19572 17.5 8.33228C17.5 9.41953 17.1375 10.6318 16.625 11.7815C16.1 12.9562 15.4 14.131 14.6375 15.1932C13.8875 16.243 13.0625 17.1928 12.3125 17.8926C11.9375 18.2425 11.5625 18.5425 11.2 18.7549C10.8625 18.9549 10.4375 19.1548 10 19.1548C9.5625 19.1548 9.1375 18.9549 8.8 18.7549C8.4375 18.5425 8.0625 18.2425 7.6875 17.8926C6.9375 17.1928 6.1125 16.243 5.3625 15.1932C4.6125 14.1435 3.9 12.9562 3.375 11.7815C2.8625 10.6193 2.5 9.41953 2.5 8.33228ZM5.8375 8.33228C5.8375 6.0328 7.7 4.17073 10 4.17073C12.3 4.17073 14.1625 6.0328 14.1625 8.33228C14.1625 10.6318 12.3 12.4938 10 12.4938C7.7 12.4938 5.8375 10.6318 5.8375 8.33228Z"
                    fill="white"
                  />
                </g>
              </svg>
              <p
                class="text-white font-semibold leading-[20px] tracking-[0.32px]"
              >
                Hanoi, Vietnam
              </p>
            </div>
          </div>
        </div>

        <!-- Follow us -->
        <div class="flex py-2 flex-col justify-center items-start gap-2 w-full">
          <p
            class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
          >
            Follow us
          </p>
          <div class="flex items-start gap-2">
            <!-- icon youtube -->
            <div class="flex p-[10px] items-start gap-2.5">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
              >
                <g clip-path="url(#clip0_11_1367)">
                  <path
                    d="M23.4947 6.38511C23.3557 5.89248 23.0905 5.44405 22.7178 5.08405C22.3452 4.72405 21.8842 4.46511 21.3789 4.33248C19.5094 3.83984 12 3.83984 12 3.83984C12 3.83984 4.49048 3.83984 2.621 4.33248C2.11574 4.46511 1.64837 4.72405 1.28206 5.08405C0.909425 5.44405 0.644162 5.89248 0.505215 6.38511C0.157846 8.24195 -0.0126799 10.1177 -4.82876e-05 11.9998C-0.0126799 13.8819 0.157846 15.7577 0.505215 17.6146C0.644162 18.1072 0.909425 18.5556 1.28206 18.9156C1.65469 19.2756 2.11574 19.5346 2.621 19.6672C4.49048 20.1598 12 20.1598 12 20.1598C12 20.1598 19.5094 20.1598 21.3789 19.6672C21.8842 19.5346 22.3515 19.2756 22.7178 18.9156C23.0905 18.5556 23.3557 18.1072 23.4947 17.6146C23.8421 15.7641 24.0126 13.8819 24 11.9998C24.0126 10.1177 23.8421 8.24195 23.4947 6.38511ZM9.59995 15.4925V8.5009L15.8336 11.9998L9.59995 15.4988V15.4925Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_11_1367">
                    <rect width="24" height="24" fill="white" />
                  </clipPath>
                </defs>
              </svg>
            </div>
            <!-- icon tiktok -->
            <div class="flex p-[10px] items-start gap-2.5">
              <svg
                width="20"
                height="23"
                viewBox="0 0 20 23"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g id="Layer_1" clip-path="url(#clip0_77_439)">
                  <path
                    id="Vector"
                    d="M10.2044 0.0820312C11.4644 0.0820312 12.7344 0.0820312 13.9944 0.0820312C13.9944 0.172031 13.9944 0.262031 13.9944 0.362031C13.9944 0.572031 14.0144 0.792031 14.0544 0.992031C14.1444 1.52203 14.3144 2.03203 14.5644 2.52203C14.8444 3.05203 15.1944 3.53203 15.6344 3.94203C16.0444 4.33203 16.5044 4.64203 17.0144 4.88203C17.7244 5.21203 18.4644 5.38203 19.2444 5.38203V9.17203C17.3244 9.16203 15.5744 8.60203 13.9944 7.49203V7.58203C13.9944 9.98203 13.9944 12.372 13.9944 14.772C13.9944 14.972 13.9944 15.182 13.9944 15.382C13.9944 15.622 13.9744 15.862 13.9444 16.092C13.8844 16.532 13.7944 16.972 13.6544 17.402C13.2644 18.562 12.6244 19.562 11.7144 20.392C10.9144 21.122 9.98444 21.642 8.93444 21.942C8.39444 22.092 7.84444 22.182 7.29444 22.202C7.27444 22.202 7.25444 22.202 7.23444 22.202H6.82444C6.82444 22.202 6.81444 22.202 6.80444 22.202C6.73444 22.202 6.65444 22.202 6.58444 22.192C6.27444 22.172 5.96444 22.132 5.65444 22.072C5.03444 21.952 4.44444 21.742 3.88444 21.462C3.17444 21.102 2.54444 20.632 1.99444 20.052C1.47444 19.512 1.05444 18.902 0.734443 18.222C0.344443 17.402 0.124443 16.542 0.0744434 15.642C0.0744434 15.592 0.0644434 15.542 0.0544434 15.492C0.0544434 15.312 0.0544434 15.122 0.0544434 14.942C0.0544434 14.892 0.0744434 14.852 0.0744434 14.802C0.0944434 14.472 0.134443 14.142 0.204443 13.812C0.334443 13.162 0.554443 12.542 0.864443 11.952C1.23444 11.252 1.70444 10.632 2.27444 10.102C3.04444 9.38203 3.92444 8.86203 4.92444 8.54203C5.42444 8.38203 5.94444 8.28203 6.46444 8.24203C6.70444 8.22203 6.95444 8.21203 7.19444 8.22203C7.40444 8.23203 7.61444 8.25203 7.82444 8.26203C7.87444 8.26203 7.93444 8.27203 7.98444 8.28203V12.152C7.98444 12.152 7.95444 12.152 7.93444 12.142C7.74444 12.082 7.54444 12.042 7.34444 12.022C6.96444 11.982 6.59444 12.012 6.22444 12.102C5.64444 12.252 5.14444 12.542 4.72444 12.972C4.48444 13.212 4.29444 13.492 4.14444 13.792C3.82444 14.442 3.73444 15.132 3.88444 15.842C4.06444 16.712 4.52444 17.392 5.26444 17.882C5.92444 18.322 6.64444 18.472 7.43444 18.372C7.82444 18.322 8.19444 18.202 8.54444 18.012C9.14444 17.672 9.59444 17.202 9.89444 16.572C10.0944 16.142 10.2044 15.692 10.2044 15.222C10.2044 10.212 10.2044 5.20203 10.2044 0.192031C10.2044 0.162031 10.2044 0.132031 10.2044 0.102031V0.0820312Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_77_439">
                    <rect
                      width="19.2"
                      height="22.12"
                      fill="white"
                      transform="translate(0.0444336 0.0820312)"
                    />
                  </clipPath>
                </defs>
              </svg>
            </div>
            <!-- icon facebook -->
            <div class="flex p-[10px] items-start gap-2.5">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g id="Facebook/Black" clip-path="url(#clip0_11_1371)">
                  <path
                    id="Vector"
                    d="M23.4028 12.052C23.4028 17.7299 19.247 22.4352 13.8091 23.2878V15.3425H16.4617L16.967 12.0583H13.8154V9.92359C13.8154 9.02675 14.2575 8.14886 15.666 8.14886H17.0996V5.35096C17.0996 5.35096 15.7986 5.12991 14.5544 5.12991C11.9586 5.12991 10.2596 6.70254 10.2596 9.55728V12.0646H7.37332V15.3489H10.2596V23.2941C4.81543 22.4352 0.659637 17.7299 0.659637 12.052C0.659637 5.77412 5.75016 0.683594 12.0344 0.683594C18.3186 0.683594 23.4091 5.77412 23.4091 12.052H23.4028Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_11_1371">
                    <rect width="24" height="24" fill="white" />
                  </clipPath>
                </defs>
              </svg>
            </div>
            <!-- icon insta -->
            <div class="flex p-[10px] items-start gap-2.5">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g id="Instagram/Black" clip-path="url(#clip0_11_1373)">
                  <path
                    id="Vector"
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M7.05273 0.072C8.33236 0.0130909 8.74036 0 12 0C15.2596 0 15.6676 0.0141818 16.9462 0.072C18.2247 0.129818 19.0975 0.333818 19.8611 0.629454C20.6607 0.931636 21.3862 1.404 21.9862 2.01491C22.5971 2.61382 23.0684 3.33818 23.3695 4.13891C23.6662 4.90255 23.8691 5.77527 23.928 7.05164C23.9869 8.33345 24 8.74145 24 12C24 15.2596 23.9858 15.6676 23.928 16.9473C23.8702 18.2236 23.6662 19.0964 23.3695 19.86C23.0684 20.6608 22.5963 21.3864 21.9862 21.9862C21.3862 22.5971 20.6607 23.0684 19.8611 23.3695C19.0975 23.6662 18.2247 23.8691 16.9484 23.928C15.6676 23.9869 15.2596 24 12 24C8.74036 24 8.33236 23.9858 7.05273 23.928C5.77636 23.8702 4.90364 23.6662 4.14 23.3695C3.33919 23.0683 2.61362 22.5963 2.01382 21.9862C1.40332 21.3869 0.930889 20.6617 0.629454 19.8611C0.333818 19.0975 0.130909 18.2247 0.072 16.9484C0.0130909 15.6665 0 15.2585 0 12C0 8.74036 0.0141818 8.33236 0.072 7.05382C0.129818 5.77527 0.333818 4.90255 0.629454 4.13891C0.931334 3.33827 1.40413 2.61307 2.01491 2.01382C2.61386 1.40346 3.3387 0.931029 4.13891 0.629454C4.90255 0.333818 5.77527 0.130909 7.05164 0.072H7.05273ZM16.8491 2.232C15.5836 2.17418 15.204 2.16218 12 2.16218C8.796 2.16218 8.41636 2.17418 7.15091 2.232C5.98036 2.28545 5.34545 2.48073 4.92218 2.64545C4.36255 2.86364 3.96218 3.12218 3.54218 3.54218C3.14405 3.92951 2.83765 4.40103 2.64545 4.92218C2.48073 5.34545 2.28545 5.98036 2.232 7.15091C2.17418 8.41636 2.16218 8.796 2.16218 12C2.16218 15.204 2.17418 15.5836 2.232 16.8491C2.28545 18.0196 2.48073 18.6545 2.64545 19.0778C2.83745 19.5982 3.144 20.0705 3.54218 20.4578C3.92945 20.856 4.40182 21.1625 4.92218 21.3545C5.34545 21.5193 5.98036 21.7145 7.15091 21.768C8.41636 21.8258 8.79491 21.8378 12 21.8378C15.2051 21.8378 15.5836 21.8258 16.8491 21.768C18.0196 21.7145 18.6545 21.5193 19.0778 21.3545C19.6375 21.1364 20.0378 20.8778 20.4578 20.4578C20.856 20.0705 21.1625 19.5982 21.3545 19.0778C21.5193 18.6545 21.7145 18.0196 21.768 16.8491C21.8258 15.5836 21.8378 15.204 21.8378 12C21.8378 8.796 21.8258 8.41636 21.768 7.15091C21.7145 5.98036 21.5193 5.34545 21.3545 4.92218C21.1364 4.36255 20.8778 3.96218 20.4578 3.54218C20.0705 3.14408 19.5989 2.83768 19.0778 2.64545C18.6545 2.48073 18.0196 2.28545 16.8491 2.232ZM10.4673 15.6993C11.3233 16.0556 12.2764 16.1037 13.1639 15.8353C14.0514 15.567 14.8182 14.9988 15.3334 14.2279C15.8485 13.457 16.0801 12.5311 15.9884 11.6085C15.8968 10.6858 15.4876 9.82361 14.8309 9.16909C14.4123 8.7507 13.906 8.43034 13.3487 8.23107C12.7914 8.0318 12.1968 7.95857 11.6078 8.01667C11.0188 8.07477 10.45 8.26274 9.94233 8.56705C9.43468 8.87136 9.00081 9.28445 8.67197 9.77656C8.34312 10.2687 8.12748 10.8276 8.04056 11.413C7.95365 11.9985 7.99762 12.596 8.16932 13.1624C8.34101 13.7288 8.63616 14.2501 9.03351 14.6888C9.43087 15.1275 9.92054 15.4726 10.4673 15.6993ZM7.63854 7.63854C8.2113 7.06579 8.89126 6.61146 9.6396 6.30148C10.3879 5.99151 11.19 5.83197 12 5.83197C12.81 5.83197 13.6121 5.99151 14.3604 6.30148C15.1087 6.61146 15.7887 7.06579 16.3615 7.63854C16.9342 8.2113 17.3885 8.89126 17.6985 9.6396C18.0085 10.3879 18.168 11.19 18.168 12C18.168 12.81 18.0085 13.6121 17.6985 14.3604C17.3885 15.1087 16.9342 15.7887 16.3615 16.3615C15.2047 17.5182 13.6359 18.168 12 18.168C10.3641 18.168 8.79527 17.5182 7.63854 16.3615C6.48181 15.2047 5.83197 13.6359 5.83197 12C5.83197 10.3641 6.48181 8.79527 7.63854 7.63854ZM19.536 6.75055C19.6779 6.61666 19.7916 6.45565 19.8701 6.27706C19.9487 6.09847 19.9907 5.90593 19.9935 5.71083C19.9964 5.51574 19.9601 5.32205 19.8867 5.14125C19.8134 4.96044 19.7045 4.79619 19.5665 4.65822C19.4285 4.52026 19.2643 4.41137 19.0835 4.33802C18.9027 4.26467 18.709 4.22834 18.5139 4.23118C18.3188 4.23403 18.1263 4.27599 17.9477 4.35458C17.7691 4.43317 17.6081 4.54679 17.4742 4.68873C17.2138 4.96476 17.0712 5.3314 17.0768 5.71083C17.0823 6.09026 17.2355 6.45259 17.5038 6.72092C17.7721 6.98924 18.1345 7.14243 18.5139 7.14796C18.8933 7.15349 19.26 7.01093 19.536 6.75055Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_11_1373">
                    <rect width="24" height="24" fill="white" />
                  </clipPath>
                </defs>
              </svg>
            </div>
            <!-- icon x -->
            <div class="flex p-[10px] items-start gap-2.5">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M2.81957 21.3709H4.42216L10.6944 14.0999L15.6818 21.3709H21.1941L13.7614 10.5884L20.5862 2.62891H18.956L13.0292 9.51428L8.27667 2.62891H2.80576L9.98979 13.0671L2.81957 21.3709ZM5.01623 3.8545H7.48919L18.9698 20.2141H16.4692L5.01623 3.8545Z"
                  fill="white"
                />
              </svg>
            </div>
            <!-- icon shoppe -->
            <div class="flex p-[10px] items-start gap-2.5">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M15.8963 17.9617C15.7567 19.1143 15.0583 20.0374 13.9765 20.4996C13.374 20.7571 12.5651 20.8961 11.9248 20.8525C10.926 20.8143 9.98763 20.5714 9.12266 20.1274C8.81365 19.9686 8.353 19.6517 7.99929 19.3549C7.9097 19.2799 7.89906 19.2318 7.95834 19.1477C7.99035 19.0995 8.04936 19.0124 8.17981 18.8213C8.369 18.5441 8.39261 18.5093 8.41389 18.4768C8.47442 18.3839 8.57277 18.3758 8.66979 18.4521C8.67998 18.4601 8.67998 18.4601 8.68767 18.4661C8.70358 18.4784 8.70358 18.4784 8.74114 18.5076C8.77914 18.5372 8.80167 18.5547 8.81079 18.5615C9.74362 19.2921 10.8301 19.7135 11.9269 19.7556C13.4529 19.7348 14.5502 19.0487 14.7468 17.9951C14.963 16.8356 14.0528 15.834 12.272 15.2757C11.7151 15.1011 10.3073 14.5376 10.0477 14.3854C8.82876 13.6702 8.25885 12.7334 8.33986 11.5763C8.46396 9.97239 9.95293 8.77613 11.8343 8.76812C12.6757 8.7664 13.5153 8.94125 14.3219 9.28112C14.6074 9.40149 15.1174 9.67897 15.2934 9.81042C15.3948 9.88488 15.4148 9.97167 15.3567 10.0653C15.3243 10.1196 15.2706 10.2057 15.1575 10.3851L15.1562 10.3871C15.0074 10.6234 15.0027 10.6308 14.9686 10.6861C14.9096 10.7759 14.8402 10.7843 14.7338 10.7168C13.8707 10.137 12.9139 9.84525 11.8616 9.82418C10.5515 9.85011 9.56962 10.6298 9.50506 11.6919C9.4879 12.6512 10.2074 13.3515 11.7615 13.8855C14.9163 14.8993 16.1235 16.0878 15.8963 17.9617ZM12.0003 1.40135C14.0542 1.40135 15.7283 3.35045 15.8066 5.79031H8.19402C8.27235 3.35045 9.9465 1.40135 12.0003 1.40135ZM22.6297 6.24902C22.6297 5.99568 22.4257 5.79031 22.1741 5.79031H17.2398C17.1188 2.56879 14.8193 0 12.0003 0C9.1814 0 6.88191 2.56879 6.76084 5.79031L1.8195 5.7904C1.57174 5.79491 1.37226 5.99856 1.37226 6.24902C1.37226 6.261 1.37271 6.27288 1.3736 6.28459H1.37012L2.0745 21.8119C2.07459 21.8552 2.0762 21.8987 2.07942 21.9426C2.08014 21.9525 2.08094 21.9623 2.08175 21.9721L2.08327 22.0049L2.08496 22.0066C2.19199 23.0871 2.97613 23.9573 4.04237 23.9975L4.04478 23.9998H19.7191C19.7265 23.9999 19.734 24 19.7414 24C19.7488 24 19.7562 23.9999 19.7636 23.9998H19.797C20.8818 23.9702 21.7613 23.0872 21.8541 21.9934L21.8553 21.9781C21.8562 21.9666 21.8571 21.9552 21.8578 21.9437C21.8595 21.9161 21.8606 21.8887 21.8611 21.8614L22.6297 6.27271C22.6301 6.26488 22.6297 6.25695 22.6297 6.24902Z"
                  fill="white"
                />
              </svg>
            </div>
          </div>
        </div>
      </div>

      <!-- Source -->
      <div class="flex py-1 flex-col justify-center items-center gap-2.5">
        <div class="flex p-1.5 items-center gap-1.5 rounded">
          <img :src="logo_2" alt="" class="w-3.5 h-3.5" />
          <p
            class="text-[#626F82] text-sm font-normal leading-[17.08px] tracking-[0.28px]"
          >
            Powered by
            <span
              class="text-[#2E353E] text-sm font-bold leading-[17.08px] tracking-[0.28px]"
              >QR Code Maketing</span
            >
          </p>
        </div>
      </div>

      <!-- Button bar -->
      <div class="flex w-full px-6 pt-4 pb-6 justify-center items-start gap-4">
        <!-- btn call -->
        <div
          class="flex px-8 h-[52px] justify-center items-center gap-3 flex-1 bg-[#F3F4F5] rounded-[100px] cursor-pointer"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="25"
            height="24"
            viewBox="0 0 25 24"
            fill="none"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M14.7713 3.17089C14.9532 2.64942 15.5234 2.37416 16.0449 2.55608C18.9179 3.55832 21.192 5.8324 22.1942 8.7054C22.3761 9.22686 22.1008 9.79706 21.5794 9.97898C21.0579 10.1609 20.4877 9.88563 20.3058 9.36416C19.5045 7.06711 17.6832 5.24579 15.3861 4.44447C14.8646 4.26256 14.5894 3.69236 14.7713 3.17089ZM8.34335 5.08935C8.10855 4.97058 7.83125 4.97058 7.59644 5.08935C7.51435 5.13087 7.40424 5.2232 6.86307 5.76437L6.71904 5.9084C6.20452 6.42292 6.07637 6.56209 5.97311 6.74591C5.85256 6.9605 5.74927 7.3577 5.75 7.60383C5.75065 7.82241 5.78127 7.95114 5.93271 8.48469C6.67402 11.0965 8.07244 13.5613 10.1307 15.6196C12.189 17.6778 14.6538 19.0763 17.2656 19.8176C17.7991 19.969 17.9279 19.9996 18.1464 20.0003C18.3926 20.001 18.7898 19.8977 19.0044 19.7772C19.1882 19.6739 19.3274 19.5457 19.8419 19.0312L20.549 19.7383L19.8419 19.0312L19.9859 18.8872C20.5271 18.346 20.6194 18.2359 20.6609 18.1538C20.7797 17.919 20.7797 17.6417 20.6609 17.4069C20.6194 17.3248 20.5271 17.2147 19.9859 16.6735L20.693 15.9664L19.9859 16.6735L19.8078 16.4955C19.4523 16.14 19.3807 16.0761 19.3301 16.0432C19.0559 15.8649 18.7023 15.8649 18.4281 16.0432C18.3775 16.0761 18.3059 16.1399 17.9503 16.4955C17.9433 16.5025 17.9361 16.5097 17.9287 16.5172C17.8473 16.5989 17.7385 16.7081 17.6077 16.8018L17.0255 15.9888L17.6077 16.8018C17.1412 17.1359 16.5088 17.2437 15.958 17.0831C15.8042 17.0383 15.6775 16.9772 15.5842 16.9322C15.5766 16.9285 15.5692 16.9249 15.562 16.9215C14.1372 16.2374 12.8027 15.3052 11.6239 14.1264C10.4451 12.9476 9.5129 11.6131 8.82878 10.1882C8.82534 10.1811 8.82178 10.1737 8.81811 10.1661C8.77308 10.0727 8.71197 9.94604 8.66715 9.79231L9.61788 9.51516L8.66715 9.7923C8.50658 9.24146 8.61441 8.6091 8.94845 8.1426L8.94845 8.1426C9.04214 8.01175 9.15142 7.90293 9.23308 7.8216C9.24056 7.81416 9.2478 7.80694 9.25478 7.79997C9.61032 7.44442 9.67421 7.37278 9.70709 7.32222L9.70709 7.32221C9.8854 7.04797 9.8854 6.69442 9.70709 6.42018C9.67421 6.36961 9.61032 6.29797 9.25478 5.94242L9.07673 5.76437C8.53556 5.2232 8.42545 5.13087 8.34335 5.08935ZM6.69375 3.30465C7.49612 2.89881 8.44368 2.89881 9.24605 3.30465C9.65432 3.51115 10.0074 3.86526 10.4003 4.25932C10.4303 4.28938 10.4605 4.31968 10.4909 4.35016L10.669 4.52821C10.6891 4.5483 10.709 4.5682 10.7288 4.58796C10.9882 4.8468 11.2203 5.07853 11.3838 5.32999L10.5455 5.87508L11.3838 5.32999C11.9931 6.26713 11.9931 7.47526 11.3838 8.4124C11.2203 8.66386 10.9882 8.89559 10.7288 9.15443C10.709 9.17418 10.6891 9.19409 10.669 9.21418C10.6444 9.23879 10.6252 9.25794 10.6087 9.27461C10.6152 9.28815 10.6226 9.30367 10.6317 9.32261C11.2195 10.5468 12.0211 11.6952 13.0381 12.7122C14.0551 13.7292 15.2035 14.5308 16.4277 15.1185L15.9948 16.02L16.4277 15.1185C16.4466 15.1276 16.4621 15.1351 16.4757 15.1415C16.4848 15.1325 16.4946 15.1227 16.5057 15.1116C16.5149 15.1025 16.5249 15.0924 16.5361 15.0813C16.5562 15.0612 16.5761 15.0412 16.5958 15.0215C16.8547 14.7621 17.0864 14.5299 17.3379 14.3664C18.275 13.7571 19.4831 13.7571 20.4203 14.3664C20.6717 14.5299 20.9035 14.7621 21.1623 15.0215C21.1821 15.0413 21.202 15.0612 21.2221 15.0813L20.5935 15.7098L21.2221 15.0813L21.4001 15.2593C21.4306 15.2898 21.4609 15.32 21.491 15.35C21.885 15.7429 22.2391 16.096 22.4456 16.5042C22.8515 17.3066 22.8515 18.2542 22.4456 19.0565C22.2391 19.4648 21.885 19.8179 21.491 20.2108C21.4609 20.2407 21.4306 20.2709 21.4001 20.3014L21.2561 20.4454C21.2341 20.4674 21.2124 20.4891 21.1909 20.5106C20.7691 20.933 20.435 21.2674 19.9839 21.5209C19.4684 21.8104 18.7317 22.002 18.1405 22.0003C17.6241 21.9987 17.2461 21.8913 16.774 21.757C16.7559 21.7519 16.7378 21.7468 16.7195 21.7416C13.788 20.9095 11.0221 19.3394 8.7165 17.0338C6.41092 14.7282 4.84074 11.9622 4.0087 9.03078C4.00351 9.01248 3.99835 8.99433 3.99323 8.97632C3.85902 8.50419 3.75155 8.12613 3.75001 7.60978C3.74825 7.01855 3.93983 6.28185 4.2294 5.76638L4.2294 5.76638C4.48283 5.31523 4.81724 4.98122 5.23964 4.55933C5.26114 4.53785 5.28287 4.51615 5.30483 4.49419L6.01193 5.20129L5.30483 4.49419L5.44886 4.35016C5.47934 4.31968 5.50954 4.28938 5.53952 4.25932C5.93241 3.86526 6.28548 3.51115 6.69375 3.30465L7.1451 4.197L6.69375 3.30465ZM13.8072 6.00844C13.9912 5.48772 14.5625 5.2148 15.0832 5.39884C17.0729 6.10209 18.6482 7.67735 19.3514 9.66703C19.5355 10.1877 19.2626 10.7591 18.7418 10.9431C18.2211 11.1272 17.6498 10.8542 17.4657 10.3335C16.9639 8.91354 15.8367 7.78641 14.4168 7.28452C13.896 7.10048 13.6231 6.52915 13.8072 6.00844Z"
              fill="#3A424E"
            />
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M14.7713 3.17089C14.9532 2.64942 15.5234 2.37416 16.0449 2.55608C18.9179 3.55832 21.192 5.8324 22.1942 8.7054C22.3761 9.22686 22.1008 9.79706 21.5794 9.97898C21.0579 10.1609 20.4877 9.88563 20.3058 9.36416C19.5045 7.06711 17.6832 5.24579 15.3861 4.44447C14.8646 4.26256 14.5894 3.69236 14.7713 3.17089ZM8.34335 5.08935C8.10855 4.97058 7.83125 4.97058 7.59644 5.08935C7.51435 5.13087 7.40424 5.2232 6.86307 5.76437L6.71904 5.9084C6.20452 6.42292 6.07637 6.56209 5.97311 6.74591C5.85256 6.9605 5.74927 7.3577 5.75 7.60383C5.75065 7.82241 5.78127 7.95114 5.93271 8.48469C6.67402 11.0965 8.07244 13.5613 10.1307 15.6196C12.189 17.6778 14.6538 19.0763 17.2656 19.8176C17.7991 19.969 17.9279 19.9996 18.1464 20.0003C18.3926 20.001 18.7898 19.8977 19.0044 19.7772C19.1882 19.6739 19.3274 19.5457 19.8419 19.0312L20.549 19.7383L19.8419 19.0312L19.9859 18.8872C20.5271 18.346 20.6194 18.2359 20.6609 18.1538C20.7797 17.919 20.7797 17.6417 20.6609 17.4069C20.6194 17.3248 20.5271 17.2147 19.9859 16.6735L20.693 15.9664L19.9859 16.6735L19.8078 16.4955C19.4523 16.14 19.3807 16.0761 19.3301 16.0432C19.0559 15.8649 18.7023 15.8649 18.4281 16.0432C18.3775 16.0761 18.3059 16.1399 17.9503 16.4955C17.9433 16.5025 17.9361 16.5097 17.9287 16.5172C17.8473 16.5989 17.7385 16.7081 17.6077 16.8018L17.0255 15.9888L17.6077 16.8018C17.1412 17.1359 16.5088 17.2437 15.958 17.0831C15.8042 17.0383 15.6775 16.9772 15.5842 16.9322C15.5766 16.9285 15.5692 16.9249 15.562 16.9215C14.1372 16.2374 12.8027 15.3052 11.6239 14.1264C10.4451 12.9476 9.5129 11.6131 8.82878 10.1882C8.82534 10.1811 8.82178 10.1737 8.81811 10.1661C8.77308 10.0727 8.71197 9.94604 8.66715 9.79231L9.61788 9.51516L8.66715 9.7923C8.50658 9.24146 8.61441 8.6091 8.94845 8.1426L8.94845 8.1426C9.04214 8.01175 9.15142 7.90293 9.23308 7.8216C9.24056 7.81416 9.2478 7.80694 9.25478 7.79997C9.61032 7.44442 9.67421 7.37278 9.70709 7.32222L9.70709 7.32221C9.8854 7.04797 9.8854 6.69442 9.70709 6.42018C9.67421 6.36961 9.61032 6.29797 9.25478 5.94242L9.07673 5.76437C8.53556 5.2232 8.42545 5.13087 8.34335 5.08935ZM6.69375 3.30465C7.49612 2.89881 8.44368 2.89881 9.24605 3.30465C9.65432 3.51115 10.0074 3.86526 10.4003 4.25932C10.4303 4.28938 10.4605 4.31968 10.4909 4.35016L10.669 4.52821C10.6891 4.5483 10.709 4.5682 10.7288 4.58796C10.9882 4.8468 11.2203 5.07853 11.3838 5.32999L10.5455 5.87508L11.3838 5.32999C11.9931 6.26713 11.9931 7.47526 11.3838 8.4124C11.2203 8.66386 10.9882 8.89559 10.7288 9.15443C10.709 9.17418 10.6891 9.19409 10.669 9.21418C10.6444 9.23879 10.6252 9.25794 10.6087 9.27461C10.6152 9.28815 10.6226 9.30367 10.6317 9.32261C11.2195 10.5468 12.0211 11.6952 13.0381 12.7122C14.0551 13.7292 15.2035 14.5308 16.4277 15.1185L15.9948 16.02L16.4277 15.1185C16.4466 15.1276 16.4621 15.1351 16.4757 15.1415C16.4848 15.1325 16.4946 15.1227 16.5057 15.1116C16.5149 15.1025 16.5249 15.0924 16.5361 15.0813C16.5562 15.0612 16.5761 15.0412 16.5958 15.0215C16.8547 14.7621 17.0864 14.5299 17.3379 14.3664C18.275 13.7571 19.4831 13.7571 20.4203 14.3664C20.6717 14.5299 20.9035 14.7621 21.1623 15.0215C21.1821 15.0413 21.202 15.0612 21.2221 15.0813L20.5935 15.7098L21.2221 15.0813L21.4001 15.2593C21.4306 15.2898 21.4609 15.32 21.491 15.35C21.885 15.7429 22.2391 16.096 22.4456 16.5042C22.8515 17.3066 22.8515 18.2542 22.4456 19.0565C22.2391 19.4648 21.885 19.8179 21.491 20.2108C21.4609 20.2407 21.4306 20.2709 21.4001 20.3014L21.2561 20.4454C21.2341 20.4674 21.2124 20.4891 21.1909 20.5106C20.7691 20.933 20.435 21.2674 19.9839 21.5209C19.4684 21.8104 18.7317 22.002 18.1405 22.0003C17.6241 21.9987 17.2461 21.8913 16.774 21.757C16.7559 21.7519 16.7378 21.7468 16.7195 21.7416C13.788 20.9095 11.0221 19.3394 8.7165 17.0338C6.41092 14.7282 4.84074 11.9622 4.0087 9.03078C4.00351 9.01248 3.99835 8.99433 3.99323 8.97632C3.85902 8.50419 3.75155 8.12613 3.75001 7.60978C3.74825 7.01855 3.93983 6.28185 4.2294 5.76638L4.2294 5.76638C4.48283 5.31523 4.81724 4.98122 5.23964 4.55933C5.26114 4.53785 5.28287 4.51615 5.30483 4.49419L6.01193 5.20129L5.30483 4.49419L5.44886 4.35016C5.47934 4.31968 5.50954 4.28938 5.53952 4.25932C5.93241 3.86526 6.28548 3.51115 6.69375 3.30465L7.1451 4.197L6.69375 3.30465ZM13.8072 6.00844C13.9912 5.48772 14.5625 5.2148 15.0832 5.39884C17.0729 6.10209 18.6482 7.67735 19.3514 9.66703C19.5355 10.1877 19.2626 10.7591 18.7418 10.9431C18.2211 11.1272 17.6498 10.8542 17.4657 10.3335C16.9639 8.91354 15.8367 7.78641 14.4168 7.28452C13.896 7.10048 13.6231 6.52915 13.8072 6.00844Z"
              fill="black"
              fill-opacity="0.2"
            />
          </svg>
          <div
            class="text-[#2E353E] font-bold leading-[21.28px] tracking-[0.32px]"
          >
            Call
          </div>
        </div>
        <!-- btn order -->
        <div
          class="flex px-8 h-[52px] justify-center items-center gap-3 flex-1 bg-[#7D9BD1] rounded-[100px] cursor-pointer"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="25"
            height="24"
            viewBox="0 0 25 24"
            fill="none"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M2.25 4C2.25 3.44772 2.69772 3 3.25 3H3.85632C4.99427 3 5.99653 3.6369 6.50428 4.58889H20.145C21.0867 4.58889 21.7955 5.44652 21.6182 6.37139L20.2104 13.7121L20.203 13.7413C19.8641 15.0701 18.6674 16 17.296 16H8.64368C7.11275 16 5.8274 14.8472 5.66138 13.3253L4.85042 5.89155C4.84728 5.86278 4.84294 5.83441 4.83746 5.80647C4.8357 5.79855 4.83403 5.7906 4.83247 5.7826C4.73214 5.33024 4.3294 5 3.85632 5H3.25C2.69772 5 2.25 4.55228 2.25 4ZM6.93836 6.58889L7.64958 13.1084C7.70492 13.6157 8.13337 14 8.64368 14H17.296C17.7448 14 18.1375 13.7013 18.2585 13.2713L19.54 6.58889H6.93836ZM5.25 19C5.25 17.8954 6.14543 17 7.25 17C8.35457 17 9.25 17.8954 9.25 19C9.25 20.1046 8.35457 21 7.25 21C6.14543 21 5.25 20.1046 5.25 19ZM16.25 19C16.25 17.8954 17.1454 17 18.25 17C19.3546 17 20.25 17.8954 20.25 19C20.25 20.1046 19.3546 21 18.25 21C17.1454 21 16.25 20.1046 16.25 19Z"
              fill="white"
            />
          </svg>
          <div
            class="text-[#fff] font-bold leading-[21.28px] tracking-[0.32px]"
          >
            Order
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
