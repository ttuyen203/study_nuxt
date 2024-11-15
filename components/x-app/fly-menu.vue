<script setup>
import icon_list from "../../assets/images/Lists icon.svg";
import icon_menu from "../../assets/images/Menu icon.svg";
import icon_profile from "../../assets/images/Profile Stroke Icon.svg";
import icon_topic from "../../assets/images/Topics Stroke Icon.svg";
import icon_bookmarks from "../../assets/images/Bookmarks icon.svg";
import icon_moments from "../../assets/images/Moments icon.svg";

const props = defineProps({
  isMenu: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <div
    :class="[
      'absolute top-0 left-0 w-[80%] bg-white h-full mt-5 transform transition-transform duration-300 ease-in-out z-50 ',
      isMenu ? 'translate-x-0' : '-translate-x-full',
    ]"
  >
    <div>
      <div class="px-6 py-6 border-b border-[#bdc5cd]">
        <div class="flex items-start justify-between">
          <div class="flex flex-col gap-1">
            <!-- Avatar -->
            <div>
              <img
                src="https://res.cloudinary.com/dymajn3ys/image/upload/v1731400068/study_nuxt/gy5jm0pctuhpp1c5x2ii.png"
                alt=""
                class="w-14 h-14 rounded-full"
              />
            </div>
            <!-- Name -->
            <div>
              <p class="text-[#141619] text-lg font-bold">To Tuyen</p>
              <p class="text-[#687684] text-base font-normal">@admin</p>
            </div>
          </div>
          <!-- Menu Icon -->
          <div class="cursor-pointer">
            <img :src="icon_menu" alt="" />
          </div>
        </div>

        <div class="flex gap-5 mt-3">
          <div class="flex items-center gap-1 cursor-pointer">
            <p class="text-[#141619] font-medium">216</p>
            <p class="text-[#687684] font-normal">Following</p>
          </div>

          <div class="flex items-center gap-1 cursor-pointer">
            <p class="text-[#141619] font-medium">111</p>
            <p class="text-[#687684] font-normal">Followers</p>
          </div>
        </div>

        <div class="mt-8 flex flex-col gap-6">
          <NuxtLink to="/x-app/user/132" class="flex items-center gap-4 cursor-pointer">
            <!-- icon -->
            <div>
              <img :src="icon_profile" alt="" />
            </div>
            <!--  -->
            <p class="text-[#141619] text-lg font-normal">Profile</p>
          </NuxtLink>

          <div class="flex items-center gap-4 cursor-pointer">
            <!-- icon -->
            <div>
              <img :src="icon_list" alt="" />
            </div>
            <!--  -->
            <p class="text-[#141619] text-lg font-normal">Lists</p>
          </div>

          <div class="flex items-center gap-4 cursor-pointer">
            <!-- icon -->
            <div>
              <img :src="icon_topic" alt="" />
            </div>
            <!--  -->
            <p class="text-[#141619] text-lg font-normal">Topics</p>
          </div>

          <div class="flex items-center gap-4 cursor-pointer">
            <!-- icon -->
            <div>
              <img :src="icon_bookmarks" alt="" />
            </div>
            <!--  -->
            <p class="text-[#141619] text-lg font-normal">Bookmarks</p>
          </div>

          <div class="flex items-center gap-4 cursor-pointer">
            <!-- icon -->
            <div>
              <img :src="icon_moments" alt="" />
            </div>
            <!--  -->
            <p class="text-[#141619] text-lg font-normal">Moments</p>
          </div>
        </div>
      </div>

      <div class="px-6 py-6 flex flex-col gap-6">
        <p class="text-[#141619] text-lg cursor-pointer">
          Settings and privacy
        </p>
        <p class="text-[#141619] text-lg cursor-pointer">Help Center</p>
      </div>
    </div>
  </div>
</template>
