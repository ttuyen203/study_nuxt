<script setup>
import add_text_icon from "../../assets/images/Add text icon.svg";
import home from "../../assets/images/Home Solid Icon.svg";
import search from "../../assets/images/Search Stroke Icon.svg";
import bell from "../../assets/images/Bell Stroke Icon.svg";
import mail from "../../assets/images/Mail Stroke Icon.svg";
</script>

<template>
  <div class="relative">
    <div class="fixed bottom-14 left-0 right-0 flex justify-center">
      <div class="flex justify-end w-[414px] px-2">
        <NuxtLink
          to="/x-app/add"
          class="bg-[#4C9EEB] px-4 py-4 rounded-full cursor-pointer"
        >
          <img :src="add_text_icon" alt="Add" />
        </NuxtLink>
      </div>
    </div>

    <div class="fixed bottom-0 left-0 right-0 flex justify-center">
      <div
        class="flex justify-between items-center bg-white px-5 py-3 w-[414px]"
      >
        <!-- Home Icon -->
        <div>
          <img :src="home" alt="" />
        </div>
        <!-- Search Icon -->
        <div>
          <img :src="search" alt="" />
        </div>
        <!-- Bell Icon -->
        <div>
          <img :src="bell" alt="" />
        </div>
        <!-- Mail Icon -->
        <div>
          <img :src="mail" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>
