<script setup>
import { ref, computed } from "vue";
import Loading from "~/components/Loading.vue";
const tienLuongMotGio = ref(6);
const tongGioLam = ref(100);
const tongLuong = computed(() => tienLuongMotGio.value * tongGioLam.value);

const handlePlus = () => {
  tienLuongMotGio.value++;
};

const isLoading = ref(true);
</script>

<template>
  <div>
    <p>Hello world</p>
    <div class="flex gap-5">
      <p>Tiền lương 1 giờ: $ {{ tienLuongMotGio }}</p>
      <button @click="handlePlus" class="btn bg-green-600 text-white py-1 px-2">
        Tăng
      </button>
    </div>
    <div>Tiền giờ làm: $ {{ tongGioLam }}</div>
    <div>Tổng lương: {{ tongLuong }}</div>

    <div v-if="isLoading">
      <Loading />
    </div>
  </div>
</template>
