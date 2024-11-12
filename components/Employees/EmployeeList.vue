<script setup>
import formatVND from "../formatVND.js";

const props = defineProps({
  _id: {
    type: [String, Object],
  },
  name: {
    type: String,
    required: true,
  },
  images: {
    type: String,
  },
  birthdate: {
    type: String,
  },
  status: {
    type: Boolean,
    default: false,
  },
  salary: {
    type: Number,
  },
  handleOpenModalUpdate: Function,
  handleDelete: Function,
});
</script>

<template>
  <tr>
    <td
      class="whitespace-nowrap px-4 py-2 font-medium text-gray-900 col-span-1"
    >
      {{ name }}
    </td>
    <td
      class="whitespace-nowrap px-4 py-2 font-medium text-gray-900 col-span-1"
    >
      <img :src="images" alt="" class="w-[40px] h-[40px]" />
    </td>
    <td class="whitespace-nowrap px-4 py-2 text-gray-700 col-span-1">
      {{ birthdate }}
    </td>
    <td class="whitespace-nowrap px-4 py-2 text-gray-700 col-span-1">
      <p
        v-if="status"
        class="py-1 bg-green-600 text-white text-center rounded-xl"
      >
        Working
      </p>
      <p v-else class="py-1 bg-gray-600 text-white text-center rounded-xl">
        Off work
      </p>
    </td>
    <td class="whitespace-nowrap px-4 py-2 text-gray-700 col-span-1">
      {{ formatVND(salary) }}
    </td>
    <td class="whitespace-nowrap px-4 py-2 col-span-1">
      <div class="flex gap-2">
        <div
          class="inline-block rounded bg-indigo-600 px-4 py-2 text-xs font-medium text-white hover:bg-indigo-700 cursor-pointer"
          @click="handleOpenModalUpdate(_id)"
        >
          Update
        </div>
        <div
          class="inline-block rounded bg-red-600 px-4 py-2 text-xs font-medium text-white hover:bg-red-700 cursor-pointer"
          @click="handleDelete(_id)"
        >
          Delete
        </div>
      </div>
    </td>
  </tr>
</template>
