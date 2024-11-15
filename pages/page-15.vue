<script setup>
// framework
import { ref } from "vue";

import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

// image
import arr_left from "../assets/images/arr_left.svg";
import arr_right from "../assets/images/arr_right.svg";
import image_7 from "../assets/images/image_7.svg";
import image_8 from "../assets/images/image_8.svg";
import image_9 from "../assets/images/image_9.svg";
import image_10 from "../assets/images/image_10.svg";
import video_banner_2 from "../assets/images/video_banner_2.svg";
import image_banner_2 from "../assets/images/image_banner_2.svg";

// icon
import logo_2 from "../assets/images/logo_2.svg";
import logo_mini from "../assets/images/logo_mini.svg";
import world from "../assets/images/world.svg";
import arr_down from "../assets/images/arr_down.svg";
import arr_up_black from "../assets/images/arr_up_black.svg";
import phone_2 from "../assets/images/phone_2.svg";
import location_2 from "../assets/images/location_2.svg";
import youtube_2 from "../assets/images/youtube_2.svg";
import tiktok_2 from "../assets/images/tiktok_2.svg";
import facebook_2 from "../assets/images/facebook_2.svg";
import instagram_2 from "../assets/images/instagram_2.svg";
import x_2 from "../assets/images/x_2.svg";
import shopee_2 from "../assets/images/shopee_2.svg";
import call_2 from "../assets/images/call_2.svg";
import cart_2 from "../assets/images/cart_2.svg";
import play from "../assets/images/play.svg";

// logic
const isOpen = ref(false);
const isView = ref(false); // btn view more
const language = ref("ENG");
const activeTabs = ref("Description");
const swiper = ref(null);

const onSwiper = (s) => {
  swiper.value = s;
};

const next = () => {
  swiper.value.slideNext();
};

const prev = () => {
  swiper.value.slidePrev();
};

const handleReadMore = () => {
  isView.value = !isView.value;
  console.log(isView.value);
};

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
    <div class="bg-[#F9F9FA] w-[390px]">
      <div class="flex w-[390px] flex-col items-center relative">
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

        <!-- Frame image -->
        <div
          class="flex pt-[55px] px-4 pb-4 flex-col justify-center items-start gap-2.5 bg-white"
        >
          <!-- Main Image -->
          <div>
            <img
              :src="image_7"
              alt=""
              class="w-[358px] h-[358px]"
              id="mainImage"
            />
          </div>
          <!-- List image -->
          <div class="flex justify-center items-center gap-2">
            <!-- arrow left -->
            <div class="cursor-pointer" @click="prev">
              <img :src="arr_left" alt="Left Arrow" />
            </div>

            <Swiper
              :slidesPerView="3"
              :modules="modules"
              class="w-[320px]"
              @swiper="onSwiper"
            >
              <swiper-slide>
                <div>
                  <img
                    :src="image_7"
                    alt="Image 7"
                    class="w-[90px] h-[90px] border hover:border-[#C38F51] cursor-pointer"
                    @click="changeImage(image_7)"
                  />
                </div>
              </swiper-slide>

              <swiper-slide>
                <div>
                  <img
                    :src="image_8"
                    alt="Image 8"
                    class="w-[90px] h-[90px] border hover:border-[#C38F51] cursor-pointer"
                    @click="changeImage(image_8)"
                  />
                </div>
              </swiper-slide>

              <swiper-slide>
                <div>
                  <img
                    :src="image_9"
                    alt="Image 9"
                    class="w-[90px] h-[90px] border hover:border-[#C38F51] cursor-pointer"
                    @click="changeImage(image_9)"
                  />
                </div>
              </swiper-slide>

              <swiper-slide>
                <div>
                  <img
                    :src="image_7"
                    alt="Image 7"
                    class="w-[90px] h-[90px] border hover:border-[#C38F51] cursor-pointer"
                    @click="changeImage(image_7)"
                  />
                </div>
              </swiper-slide>

              <swiper-slide>
                <div>
                  <img
                    :src="image_8"
                    alt="Image 8"
                    class="w-[90px] h-[90px] border hover:border-[#C38F51] cursor-pointer"
                    @click="changeImage(image_8)"
                  />
                </div>
              </swiper-slide>
            </Swiper>

            <!-- arrow right -->
            <div class="cursor-pointer" @click="next">
              <img :src="arr_right" alt="Right Arrow" />
            </div>
          </div>
        </div>

        <!-- Text -->
        <div class="flex p-4 justify-center items-center gap-2.5 bg-[#C38F51]">
          <p
            class="text-white text-base font-normal leading-[21.28px] tracking-[0.32px]"
          >
            Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse
            molestie consequat, vel illum dolore eu feugiat nulla facilisis at
            vero
          </p>
        </div>

        <!-- Infor Product -->
        <div class="flex flex-col gap-4 items-center w-full">
          <!-- Name, price, size -->
          <div class="flex px-4 flex-col items-center bg-white w-full">
            <!-- Name, price -->
            <div
              class="flex py-4 flex-col items-center gap-2.5 border-b border-[#E0E2E6] w-full"
            >
              <p
                class="text-[#2E353E] text-xl font-semibold leading-[25px] tracking-[0.4px]"
              >
                Necklace
              </p>
              <p
                class="text-[#2E353E] text-base font-medium leading-[21.28px] tracking-[0.32px]"
              >
                $50.00 USD
              </p>
            </div>
            <!-- Size -->
            <div class="flex py-4 justify-center items-center gap-4">
              <p
                class="text-[#2E353E] text-base font-semibold leading-[21.28px] tracking-[0.32px]"
              >
                Size
              </p>

              <div class="flex items-start gap-2">
                <div
                  class="flex h-[36px] py-2 px-6 justify-center items-center gap-2.5 rounded-[100px] border border-[#E0E2E6] cursor-pointer"
                >
                  <p
                    class="text-[#2E353E] text-base font-normal leading-[21.28px] tracking-[0.32px]"
                  >
                    X
                  </p>
                </div>

                <div
                  class="flex h-[36px] py-2 px-6 justify-center items-center gap-2.5 rounded-[100px] border border-[#E0E2E6] cursor-pointer"
                >
                  <p
                    class="text-[#2E353E] text-base font-normal leading-[21.28px] tracking-[0.32px]"
                  >
                    XS
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- Desc -->
          <div
            class="flex py-6 px-4 flex-col items-center gap-4 bg-white w-full"
          >
            <!-- Nav -->
            <div class="flex justify-center items-center gap-2">
              <div
                @click="activeTabs = 'Description'"
                class="flex py-2 px-6 justify-center items-center gap-2.5 rounded-[100px] cursor-pointer"
                :class="
                  activeTabs === 'Description'
                    ? 'bg-[#C38F51] text-white'
                    : 'text-[#626F82]'
                "
              >
                <p
                  class="text-base font-semibold leading-[21.28px] tracking-[0.32px]"
                >
                  Description
                </p>
              </div>
              <div
                @click="activeTabs = 'Information'"
                class="flex py-2 px-6 justify-center items-center gap-2.5 rounded-[100px] cursor-pointer"
                :class="
                  activeTabs === 'Information'
                    ? 'bg-[#C38F51] text-white'
                    : 'text-[#626F82]'
                "
              >
                <p
                  class="text-base font-semibold leading-[21.28px] tracking-[0.32px]"
                >
                  Information
                </p>
              </div>
            </div>

            <!-- Desc content desc-->
            <div
              class="flex flex-col items-center gap-1"
              v-if="activeTabs === 'Description'"
            >
              <div class="flex flex-col items-start gap-1">
                <p
                  :class="isView ? '' : 'line-clamp-3'"
                  class="text-[#2E353E] text-center"
                >
                  Duis autem vel eum iriure dolor in hendrerit in vulputate
                  velit esse molestie consequat, vel illum dolore eu feugiat
                  nulla facilisis at vero eros et accumsan et iusto odio
                  dignissim qui blandit praesent luptatum zzril delenit augue
                  duis dolore te feugait nulla facilisi.
                </p>
              </div>
              <div
                class="flex items-center gap-2 rounded-[100px]"
                @click="handleReadMore"
              >
                <p
                  class="text-[#C38F51] font-semibold leading-[21.28px] tracking-[0.32px] cursor-pointer"
                >
                  {{ isView ? "Collapse" : "Readmore" }}
                </p>
              </div>
            </div>

            <!-- Desc content infor-->
            <div
              class="flex flex-col items-center gap-1"
              v-if="activeTabs === 'Information'"
            >
              <div class="flex flex-col items-start gap-1">
                <p
                  :class="isView ? '' : 'line-clamp-3'"
                  class="text-[#2E353E] text-center"
                >
                  Demo desc information page
                </p>
              </div>
              <div
                class="flex items-center gap-2 rounded-[100px]"
                @click="handleReadMore"
              >
                <p
                  class="text-[#C38F51] font-semibold leading-[21.28px] tracking-[0.32px] cursor-pointer"
                >
                  {{ isView ? "Collapse" : "Readmore" }}
                </p>
              </div>
            </div>
          </div>

          <!-- Video banner -->
          <div
            class="flex flex-col items-start gap-2.5 border border-[#E0E2E6] relative"
          >
            <img :src="video_banner_2" alt="" />
            <div
              class="absolute left-[157px] bottom-[75.19px] p-2.5 flex justify-center items-center w-[60px] h-[60px] gap-2.5 border border-[#ffffff33] bg-[#ffffff33] rounded-full cursor-pointer"
            >
              <img :src="play" alt="" />
            </div>
          </div>

          <!-- Image banner -->
          <div class="flex flex-col items-start gap-2.5 border borde-[#E0E2E6]">
            <img :src="image_banner_2" alt="" />
          </div>

          <!-- Related products -->
          <div
            class="flex py-6 px-4 flex-col items-center gap-4 bg-white w-full"
          >
            <!-- Related products title -->
            <div class="flex justify-center items-center gap-2">
              <p
                class="text-[#2E353E] text-2xl font-semibold leading-[30px] tracking-[0.48px]"
              >
                Related products
              </p>
            </div>
            <!-- Related products content -->
            <div class="flex items-start gap-4 w-full">
              <Swiper
                :slidesPerView="2.3"
                :spaceBetween="40"
                :pagination="{
                  clickable: true,
                }"
                :modules="modules"
              >
                <!-- Slide 1 -->
                <swiper-slide>
                  <div class="flex w-[160px] flex-col items-center gap-2">
                    <!-- image product -->
                    <div>
                      <img :src="image_10" alt="" class="w-[160px] h-[160px]" />
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <p
                        class="text-[#2E353E] font-semibold leading-[21.28px] tracking-[0.32px]"
                      >
                        Waistband
                      </p>
                      <p
                        class="text-[#C38F51] text-sm font-semibold leading-[18.62px] tracking-[0.28px]"
                      >
                        $50.00 USD
                      </p>
                    </div>
                  </div>
                </swiper-slide>

                <!-- Slide 2 -->
                <swiper-slide>
                  <div class="flex w-[160px] flex-col items-center gap-2">
                    <!-- image product -->
                    <div>
                      <img :src="image_8" alt="" class="w-[160px] h-[160px]" />
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <p
                        class="text-[#2E353E] font-semibold leading-[21.28px] tracking-[0.32px]"
                      >
                        Nawarat ring
                      </p>
                      <p
                        class="text-[#C38F51] text-sm font-semibold leading-[18.62px] tracking-[0.28px]"
                      >
                        $50.00 USD
                      </p>
                    </div>
                  </div>
                </swiper-slide>

                <!-- Slide 3 -->
                <swiper-slide>
                  <div class="flex w-[160px] flex-col items-center gap-2">
                    <!-- image product -->
                    <div>
                      <img :src="image_10" alt="" class="w-[160px] h-[160px]" />
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <p
                        class="text-[#2E353E] font-semibold leading-[21.28px] tracking-[0.32px]"
                      >
                        Waistband
                      </p>
                      <p
                        class="text-[#C38F51] text-sm font-semibold leading-[18.62px] tracking-[0.28px]"
                      >
                        $50.00 USD
                      </p>
                    </div>
                  </div>
                </swiper-slide>

                <!-- Slide 4 -->
                <swiper-slide>
                  <div class="flex w-[160px] flex-col items-center gap-2">
                    <!-- image product -->
                    <div>
                      <img :src="image_8" alt="" class="w-[160px] h-[160px]" />
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <p
                        class="text-[#2E353E] font-semibold leading-[21.28px] tracking-[0.32px]"
                      >
                        Nawarat ring
                      </p>
                      <p
                        class="text-[#C38F51] text-sm font-semibold leading-[18.62px] tracking-[0.28px]"
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
          class="flex p-4 justify-center items-center flex-col gap-2.5 bg-[#f9f9fa] w-full"
        >
          <el-collapse v-model="activeNames" class="w-full">
            <!-- Store -->
            <el-collapse-item name="store">
              <template #title>
                <div
                  class="flex py-4 justify-between items-center w-full bg-[#f9f9fa]"
                >
                  <p
                    class="text-[#2E353E] text-lg font-semibold leading-[22.5px] tracking-[0.36px]"
                  >
                    Store
                  </p>
                  <img :src="arr_up_black" alt="" />
                </div>
              </template>
              <!-- Collapse item store-->
              <div class="flex flex-col gap-4 w-full pb-5 bg-[#f9f9fa]">
                <!-- QR and name -->
                <div class="flex gap-4 items-center">
                  <img
                    :src="logo_2"
                    alt=""
                    class="w-[52px] h-[52px] rounded-[4px] border border-[#E0E2E6]"
                  />
                  <div class="flex flex-col gap-1 flex-1">
                    <p
                      class="text-[#2E353E] text-lg font-semibold leading-[22.5px] tracking-[0.36px]"
                    >
                      SofaKart
                    </p>
                    <p
                      class="text-[#626F82] text-base font-normal leading-[21.28px] tracking-[0.32px]"
                    >
                      Business owned
                    </p>
                  </div>
                </div>

                <!-- Phone number and address -->
                <div class="flex flex-col gap-3">
                  <!-- Phone number -->
                  <div class="flex items-center gap-2">
                    <img :src="phone_2" alt="" />
                    <p
                      class="text-[#2E353E] text-base font-normal leading-[21.28px] tracking-[0.32px]"
                    >
                      0988 777 777
                    </p>
                  </div>
                  <!-- Address -->
                  <div class="flex items-center gap-2">
                    <img :src="location_2" alt="" />
                    <p
                      class="text-[#2E353E] font-normal leading-[21.28px] tracking-[0.32px] text-base"
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
                  class="flex py-4 justify-between items-center w-full bg-[#f9f9fa]"
                >
                  <p
                    class="text-[#2E353E] text-lg font-semibold leading-[22.5px] tracking-[0.36px]"
                  >
                    Company
                  </p>
                  <img :src="arr_up_black" alt="" />
                </div>
              </template>
              <!-- Collapse item store-->
              <div class="flex flex-col gap-4 w-full pb-5 bg-[#f9f9fa]">
                <!-- QR and name -->
                <div class="flex gap-4 items-center">
                  <img
                    :src="logo_2"
                    alt=""
                    class="w-[52px] h-[52px] rounded-[4px] border border-[#E0E2E6]"
                  />
                  <div class="flex flex-col gap-1 flex-1">
                    <p
                      class="text-[#2E353E] text-lg font-semibold leading-[22.5px] tracking-[0.36px]"
                    >
                      SofaKart
                    </p>
                    <p
                      class="text-[#626F82] text-base font-normal leading-[21.28px] tracking-[0.32px]"
                    >
                      Business owned
                    </p>
                  </div>
                </div>

                <!-- Phone number and address -->
                <div class="flex flex-col gap-3">
                  <!-- Phone number -->
                  <div class="flex items-center gap-2">
                    <img :src="phone_2" alt="" />
                    <p
                      class="text-[#2E353E] text-base font-normal leading-[21.28px] tracking-[0.32px]"
                    >
                      0988 777 777
                    </p>
                  </div>
                  <!-- Address -->
                  <div class="flex items-center gap-2">
                    <img :src="location_2" alt="" />
                    <p
                      class="text-[#2E353E] font-normal leading-[21.28px] tracking-[0.32px] text-base"
                    >
                      Hanoi, Vietnam
                    </p>
                  </div>
                </div>
              </div>
            </el-collapse-item>
          </el-collapse>

          <!-- Follow us -->
          <div
            class="flex py-2 flex-col justify-center items-start gap-4 w-full"
          >
            <p
              class="text-[#2E353E] text-lg font-semibold leading-[22.5px] tracking-[0.36px]"
            >
              Follow us
            </p>
            <div class="flex items-start gap-2">
              <!-- Youtube -->
              <div class="bg-[#C38F51] p-2.5 rounded-full w-11">
                <img :src="youtube_2" alt="" />
              </div>

              <!-- Tiktok -->
              <div class="bg-[#C38F51] p-2.5 rounded-full w-11">
                <img :src="tiktok_2" alt="" />
              </div>

              <!-- Facebook -->
              <div class="bg-[#C38F51] p-2.5 rounded-full w-11">
                <img :src="facebook_2" alt="" />
              </div>

              <!-- Insta -->
              <div class="bg-[#C38F51] p-2.5 rounded-full w-11">
                <img :src="instagram_2" alt="" />
              </div>

              <!-- Twitter -->
              <div class="bg-[#C38F51] p-2.5 rounded-full w-11">
                <img :src="x_2" alt="" />
              </div>

              <!-- Shopee -->
              <div class="bg-[#C38F51] p-2.5 rounded-full w-11">
                <img :src="shopee_2" alt="" />
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
            class="flex px-6 pt-4 pb-6 justify-center items-start gap-4 bg-white w-[390px]"
          >
            <!-- btn call -->
            <div
              class="flex px-8 h-[52px] justify-center items-center gap-3 flex-1 bg-[#F3F4F5] rounded-[100px] cursor-pointer"
            >
              <img :src="call_2" alt="" />
              <div
                class="text-[#2E353E] font-bold leading-[21.28px] tracking-[0.32px]"
              >
                Call
              </div>
            </div>
            <!-- btn order -->
            <div
              class="flex px-8 h-[52px] justify-center items-center gap-3 flex-1 bg-[#C38F51] rounded-[100px] cursor-pointer"
            >
              <img :src="cart_2" alt="" />
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
</style>
