<template>
  <div>
    <nav
      class="border-solid border-gray-200 w-full border-b py-3 bg-white z-50 bg-inherit"
    >
      <div class="container mx-auto bg-white">
        <div class="w-full flex flex-col lg:flex-row">
          <div class="flex justify-between lg:flex-row">
            <p class="pl-4">Logo</p>
          </div>
          <div
            class="hidden w-full lg:flex lg:pl-11"
            id="navbar-default-example"
          >
            <ul
              class="flex items-center flex-col mt-4 lg:mt-0 lg:ml-auto lg:flex-row gap-4"
            >
              <li>
                <NuxtLink
                  to="/"
                  class="flex items-center justify-between text-gray-500 text-sm lg:text-base font-medium hover:text-indigo-700 transition-all duration-500 mb-2 lg:mr-6 md:mb-0 md:mr-3"
                  >Home</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/page-16"
                  class="flex items-center justify-between text-gray-500 text-sm lg:text-base font-medium hover:text-indigo-700 transition-all duration-500 mb-2 lg:mr-6 md:mb-0 md:mr-3"
                  >Page 16</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/employee-management"
                  class="flex items-center justify-between text-gray-500 text-sm lg:text-base font-medium hover:text-indigo-700 transition-all duration-500 mb-2 lg:mr-6 md:mb-0 md:mr-3"
                  >Employee Management</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/register"
                  class="flex items-center justify-between text-gray-500 text-sm lg:text-base font-medium hover:text-indigo-700 transition-all duration-500 mb-2 lg:mr-6 md:mb-0 md:mr-3"
                  >Register</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/login"
                  class="flex items-center justify-between text-gray-500 text-sm lg:text-base font-medium hover:text-indigo-700 transition-all duration-500 mb-2 lg:mr-6 md:mb-0 md:mr-3"
                  >Login</NuxtLink
                >
              </li>
              <li>
                <NuxtLink
                  to="/x-app/home"
                  class="flex items-center justify-between text-gray-500 text-sm lg:text-base font-medium hover:text-indigo-700 transition-all duration-500 mb-2 lg:mr-6 md:mb-0 md:mr-3"
                  >X app</NuxtLink
                >
              </li>
              <!-- navbar next -->
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>
