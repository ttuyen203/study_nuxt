<template>
  <div class="flex justify-center items-center px-5 bg-gray-500 h-screen">
    <div class="w-[414px] bg-white mt-5 px-5 py-2">
      <div class="flex flex-col gap-5">
        <!-- Btn -->
        <div class="flex justify-between items-center">
          <NuxtLink to="/x-app/home" class="text-[#4C9EEB] cursor-pointer">Cancel</NuxtLink>
          <p
            class="text-white py-2 px-4 rounded-[100px] bg-[#4C9EEB] cursor-pointer"
          >
            Tweet
          </p>
        </div>

        <!--  -->
        <div class="flex items-start gap-4">
          <div>
            <img
              src="https://res.cloudinary.com/dymajn3ys/image/upload/v1731400068/study_nuxt/gy5jm0pctuhpp1c5x2ii.png"
              alt=""
              class="w-9 h-9"
            />
          </div>
          <div>
            <textarea
              placeholder="What's happening?"
              class="placeholder:text-[#687684] placeholder:text-lg w-80 h-20 focus:outline-none focus:border-none resize-none overflow-hidden"
            ></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
