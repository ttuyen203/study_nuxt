<script setup>
// image
import { ref } from "vue";
import image_1 from "../assets/images/image_1.svg";
import image_2 from "../assets/images/image_2.svg";
import image_3 from "../assets/images/image_3.svg";
import image_4 from "../assets/images/image_4.svg";
import image_5 from "../assets/images/image_5.svg";
import image_6 from "../assets/images/image_6.svg";
import video_banner from "../assets/images/video_banner.svg";
import img_banner from "../assets/images/image_banner.svg";

// icon
import world from "../assets/images/world.svg";
import arr_down from "../assets/images/arr_down.svg";
import arr_up from "../assets/images/arr_up.svg";
import logo_mini from "../assets/images/logo_mini.svg";
import logo from "../assets/images/logo.svg";
import phone from "../assets/images/phone.svg";
import location from "../assets/images/location.svg";
import youtube from "../assets/images/youtube.svg";
import tiktok from "../assets/images/tiktok.svg";
import facebook from "../assets/images/facebook.svg";
import instagram from "../assets/images/instagram.svg";
import x from "../assets/images/x.svg";
import shoppe from "../assets/images/shopee.svg";
import call from "../assets/images/call.svg";
import cart from "../assets/images/cart.svg";

// framework
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

// logic
const isOpen = ref(false);
const language = ref("ENG");

const activeNames = ref(["store"]);

const activeTab = ref("Description");

const changeImage = (src) => {
  document.getElementById("mainImage").src = src;
};

const changeLanguage = (lang) => {
  language.value = lang;
  isOpen.value = false;
};
</script>

<template>
  <div class="flex justify-center items-center bg-gray-200">
    <div class="bg-white w-[390px] relative">
      <!-- frame btn change language -->
      <div class="absolute right-0">
        <div class="flex-col pt-4 px-6">
          <div
            @click="isOpen = !isOpen"
            class="flex items-center gap-1 py-1.5 px-3 bg-white rounded-[100px] mb-[7px]"
          >
            <div>
              <img :src="world" alt="" />
            </div>
            <p class="text-[#2E353E] text-sm font-semibold cursor-pointer">
              {{ language }}
            </p>
            <div>
              <img :src="arr_down" alt="" />
            </div>
          </div>
          <!-- box content change language -->
          <div
            v-if="isOpen"
            class="border shadow-gray-400 shadow-inner transition-all duration-200 ease-in-out"
          >
            <div
              @click="changeLanguage('ENG')"
              class="text-[#2E353E] text-sm font-semibold bg-white text-center py-2 hover:bg-[#e1ecdc] cursor-pointer"
            >
              ENG
            </div>
            <div
              @click="changeLanguage('VIE')"
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
              :src="image_1"
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
                :src="image_1"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(image_1)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="image_2"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(image_2)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="image_3"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(image_3)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="image_4"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(image_4)"
              />
            </div>

            <!-- image item -->
            <div>
              <img
                :src="image_5"
                alt=""
                class="w-[60px] h-[60px] rounded-2xl hover:border hover:border-[#1E306E] cursor-pointer"
                @click="changeImage(image_5)"
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
              @click="activeTab = 'Description'"
              :class="
                activeTab === 'Description'
                  ? 'text-[#1E306E] font-bold leading-[21px] tracking-[0.02em] border-b-2 border-[#1E306E] px-6 pb-4 cursor-pointer'
                  : 'text-[#626F82] leading-[21px] tracking-[0.02em] font-bold px-6 pb-4 cursor-pointer'
              "
            >
              Description
            </div>
            <div
              @click="activeTab = 'Information'"
              :class="
                activeTab === 'Information'
                  ? 'text-[#1E306E] font-bold leading-[21px] tracking-[0.02em] border-b-2 border-[#1E306E] px-6 pb-4 cursor-pointer'
                  : 'text-[#626F82] leading-[21px] tracking-[0.02em] font-bold px-6 pb-4 cursor-pointer'
              "
            >
              Information
            </div>
          </div>

          <!-- Desc content -->
          <!--  Desc content desc -->
          <div v-if="activeTab === 'Description'">
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

          <!--  Desc content information -->
          <div v-if="activeTab === 'Information'">
            <p
              class="text-[#2E353E] font-normal leading-[21px] tracking-[0.02em] text-base"
            >
              Demo information
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
                  <img :src="image_6" alt="" />
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
                  <img :src="image_6" alt="" />
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
        <el-collapse v-model="activeNames" class="w-full">
          <!-- Store -->
          <el-collapse-item name="store">
            <template #title>
              <div
                class="flex py-4 justify-between items-center w-full bg-[#7D9BD1]"
              >
                <p
                  class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
                >
                  Store
                </p>
                <img :src="arr_up" alt="" />
              </div>
            </template>
            <!-- Collapse item store-->
            <div class="flex flex-col gap-4 w-full pb-5 bg-[#7D9BD1]">
              <!-- QR and name -->
              <div class="flex gap-4 items-center">
                <img
                  :src="logo"
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
                  <img :src="phone" alt="" />
                  <p
                    class="text-white font-semibold leading-[20px] tracking-[0.32px] text-base"
                  >
                    0988 777 777
                  </p>
                </div>
                <!-- Address -->
                <div class="flex items-center gap-2">
                  <img :src="location" alt="" />
                  <p
                    class="text-white font-semibold leading-[20px] tracking-[0.32px] text-base"
                  >
                    Hanoi, Vietnam
                  </p>
                </div>
              </div>
            </div>
          </el-collapse-item>

          <!-- Company -->
          <el-collapse-item name="company">
            <template #title>
              <div
                class="flex py-4 justify-between items-center w-full bg-[#7D9BD1]"
              >
                <p
                  class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
                >
                  Company
                </p>
                <img :src="arr_up" alt="" />
              </div>
            </template>
            <!-- Collapse item Company-->
            <div class="flex flex-col gap-4 w-full pb-5 bg-[#7D9BD1]">
              <!-- QR and name -->
              <div class="flex gap-4 items-center">
                <img
                  :src="logo"
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
                  <img :src="phone" alt="" />
                  <p
                    class="text-white font-semibold leading-[20px] tracking-[0.32px] text-base"
                  >
                    0988 777 777
                  </p>
                </div>
                <!-- Address -->
                <div class="flex items-center gap-2">
                  <img :src="location" alt="" />
                  <p
                    class="text-white font-semibold leading-[20px] tracking-[0.32px] text-base"
                  >
                    Hanoi, Vietnam
                  </p>
                </div>
              </div>
            </div>
          </el-collapse-item>
        </el-collapse>

        <!-- Follow us -->
        <div class="flex py-2 flex-col justify-center items-start gap-2 w-full">
          <p
            class="text-white text-lg font-bold leading-[22.5px] tracking-[0.36px]"
          >
            Follow us
          </p>
          <div class="flex items-center gap-2">
            <!-- icon youtube -->
            <div class="flex p-[10px] items-start gap-2.5">
              <img :src="youtube" alt="" class="cursor-pointer" />
            </div>
            <!-- icon tiktok -->
            <div class="flex p-[10px] items-start gap-2.5">
              <img :src="tiktok" alt="" class="cursor-pointer" />
            </div>
            <!-- icon facebook -->
            <div class="flex p-[10px] items-start gap-2.5">
              <img :src="facebook" alt="" class="cursor-pointer" />
            </div>
            <!-- icon insta -->
            <div class="flex p-[10px] items-start gap-2.5">
              <img :src="instagram" alt="" class="cursor-pointer" />
            </div>
            <!-- icon x -->
            <div class="flex p-[10px] items-start gap-2.5">
              <img :src="x" alt="" class="cursor-pointer" />
            </div>
            <!-- icon shoppe -->
            <div class="flex p-[10px] items-start gap-2.5">
              <img :src="shoppe" alt="" class="cursor-pointer" />
            </div>
          </div>
        </div>
      </div>

      <!-- Source -->
      <div
        class="flex py-1 flex-col justify-center items-center gap-2.5 mb-[92px]"
      >
        <div class="flex p-1.5 items-center gap-1.5 rounded">
          <img :src="logo_mini" alt="" class="w-3.5 h-3.5" />
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
      <div class="fixed bottom-0 right-0 left-0 flex justify-center z-50">
        <div
          class="flex px-6 pt-4 pb-6 justify-center items-start gap-4 w-[390px] bg-white"
        >
          <div></div>
          <!-- btn call -->
          <div
            class="flex px-8 h-[52px] justify-center items-center gap-3 flex-1 bg-[#F3F4F5] rounded-[100px] cursor-pointer"
          >
            <img :src="call" alt="" />
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
            <img :src="cart" alt="" />
            <div
              class="text-[#fff] font-bold leading-[21.28px] tracking-[0.32px]"
            >
              Order
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.el-collapse-item__arrow {
  display: none !important;
}

.el-collapse-item__content {
  padding: 0;
  margin: 0;
}

.el-collapse-item__wrap {
  border-bottom: none;
}
</style>
