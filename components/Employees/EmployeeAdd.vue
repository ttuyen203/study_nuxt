<script setup>
const props = defineProps({
  isOpenModalAdd: {
    type: Boolean,
    default: false,
  },
  handleAdd: {
    type: Function,
  },
  isLoadingImage: {
    type: Boolean,
    default: false,
  },
  image: {
    type: String,
    default: "",
  },
  handleChangeImage: {
    type: Function,
  },
  formData: {
    type: Object,
  },
  handleCloseModalAdd: {
    type: Function,
  },
});
</script>

<template>
  <div
    v-if="isOpenModalAdd"
    class="fixed overflow-y-auto bg-slate-600 inset-0 bg-opacity-50"
  >
    <div class="flex justify-center items-center">
      <form class="bg-white p-4" @submit.prevent="handleAdd">
        <div class="space-y-12">
          <div class="border-b border-gray-900/10 pb-12">
            <h2 class="text-base/7 font-semibold text-gray-900">Profile</h2>
            <p class="mt-1 text-sm/6 text-gray-600">
              This information will be displayed publicly so be careful what you
              share.
            </p>

            <div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
              <div class="col-span-full">
                <label
                  for="photo"
                  class="block text-sm/6 font-medium text-gray-900"
                  >Photo</label
                >
                <div v-if="isLoadingImage">
                  <Loading />
                </div>
                <div class="mt-2 flex items-center gap-x-3">
                  <div v-if="image">
                    <img :src="image" alt="" class="w-12 h-12" />
                  </div>
                  <div v-else>
                    <svg
                      class="h-12 w-12 text-gray-300"
                      viewBox="0 0 24 24"
                      fill="currentColor"
                      aria-hidden="true"
                      data-slot="icon"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M18.685 19.097A9.723 9.723 0 0 0 21.75 12c0-5.385-4.365-9.75-9.75-9.75S2.25 6.615 2.25 12a9.723 9.723 0 0 0 3.065 7.097A9.716 9.716 0 0 0 12 21.75a9.716 9.716 0 0 0 6.685-2.653Zm-12.54-1.285A7.486 7.486 0 0 1 12 15a7.486 7.486 0 0 1 5.855 2.812A8.224 8.224 0 0 1 12 20.25a8.224 8.224 0 0 1-5.855-2.438ZM15.75 9a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0Z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </div>

                  <input
                    type="file"
                    id="avatar"
                    class="hidden"
                    accept="image/*"
                    @change="handleChangeImage"
                  />
                  <label for="avatar">
                    <div
                      class="rounded-md bg-white px-2.5 py-1.5 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50"
                    >
                      Change
                    </div>
                  </label>
                </div>
              </div>
            </div>
          </div>

          <div class="border-b border-gray-900/10 pb-12">
            <h2 class="text-base/7 font-semibold text-gray-900">
              Personal Information
            </h2>
            <p class="mt-1 text-sm/6 text-gray-600">
              Use a permanent address where you can receive mail.
            </p>

            <div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
              <div class="sm:col-span-4">
                <label
                  for="name"
                  class="block text-sm/6 font-medium text-gray-900"
                  >Name</label
                >
                <div class="mt-2">
                  <input
                    type="text"
                    placeholder="Enter your name"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm/6 px-2"
                    v-model="formData.name"
                  />
                </div>
              </div>

              <div class="sm:col-span-4">
                <label class="block text-sm/6 font-medium text-gray-900"
                  >Birth Date</label
                >
                <div class="mt-2">
                  <input
                    type="date"
                    autocomplete="email"
                    v-model="formData.birthdate"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm/6 px-2"
                  />
                </div>
              </div>

              <div class="sm:col-span-4">
                <label
                  for="street-address"
                  class="block text-sm/6 font-medium text-gray-900"
                  >Salary</label
                >
                <div class="mt-2">
                  <input
                    type="number"
                    v-model="formData.salary"
                    name="street-address"
                    id="street-address"
                    autocomplete="street-address"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm/6 px-2"
                  />
                </div>
              </div>

              <div class="sm:col-span-3">
                <div>
                  <label
                    for="country"
                    class="block text-sm/6 font-medium text-gray-900"
                    >Status</label
                  >
                  <input
                    type="checkbox"
                    class="w-4 h-4"
                    v-model="formData.status"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-6 flex items-center justify-end gap-x-6">
          <button
            type="button"
            @click="handleCloseModalAdd"
            class="text-sm/6 font-semibold text-gray-900"
          >
            Cancel
          </button>

          <button
            type="submit"
            class="rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          >
            Save
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
