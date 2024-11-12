<script setup>
import axios from "axios";
import Swal from "sweetalert2";
import { toast } from "vue3-toastify";
import EmployeeList from "~/components/Employees/EmployeeList.vue";
import Loading from "~/components/Loading.vue";
import baseUrl from "~/configs/baseUrl";
import CLOUDINARY_URL from "~/configs/cloundinary";

const datas = ref([]);
const isOpenModalAdd = ref(false);
const isOpenModalUpdate = ref(false);
const idEmployee = ref("");
const image = ref("");
const formData = reactive({
  name: "",
  birthdate: "",
  status: false,
  salary: "",
});

const formDataUpdate = reactive({
  name: "",
  birthdate: "",
  status: false,
  salary: "",
});

const searchValue = ref("");

const isLoading = ref(false);
const isLoadingImage = ref(false);

const resetForm = () => {
  formData.name = "";
  formData.birthdate = "";
  formData.status = "";
  formData.salary = "";
  image.value = "";
};

const fetchData = () => {
  isLoading.value = true;
  axios
    .get(baseUrl + "/employees")
    .then((res) => {
      console.log(res.data);
      datas.value = res.data;
    })
    .catch((err) => {
      console.log(err);
    })
    .finally(() => {
      isLoading.value = false;
    });
};

const filterEmploy = computed(() => {
  return datas.value.filter((data) =>
    data.name.toLowerCase().includes(searchValue.value.toLowerCase())
  );
});

const handleOpenModalAdd = () => {
  isOpenModalAdd.value = true;
};

const handleCloseModalAdd = () => {
  isOpenModalAdd.value = false;
  resetForm();
};

const handleOpenModalUpdate = (id) => {
  isOpenModalUpdate.value = true;
  idEmployee.value = id;

  axios
    .get(baseUrl + "/employees/" + id)
    .then((res) => {
      console.log(res);
      formDataUpdate.name = res.data.name;
      formDataUpdate.birthdate = res.data.birthdate;
      formDataUpdate.status = res.data.status;
      formDataUpdate.salary = res.data.salary;
      image.value = res.data.images;
    })
    .catch((err) => {
      console.log(err);
    });
};

const handleCloseModalUpdate = () => {
  isOpenModalUpdate.value = false;
  resetForm();
};

const handleUploadImage = async (file) => {
  const formData = new FormData();
  formData.append("file", file);
  formData.append("upload_preset", "study_nuxt");

  isLoadingImage.value = true;
  const res = await axios.post(CLOUDINARY_URL, formData);
  console.log(res);

  isLoadingImage.value = false;

  return res.data.secure_url;
};

const handleChangeImage = async (e) => {
  const file = e.target.files[0];
  console.log(file);
  image.value = await handleUploadImage(file);
  console.log(image.value);
};

const handleAdd = async () => {
  const dataAdd = {
    ...formData,
    images: image.value,
  };

  console.log(dataAdd);

  await axios
    .post(baseUrl + "/employees", dataAdd)
    .then((res) => {
      console.log(res);
      isOpenModalAdd.value = false;
      resetForm();
      fetchData();
      toast.success("Added successfully!");
    })
    .catch((err) => {
      console.log(err);
    });
};

const handleAUpdate = async (id) => {
  const dataUpdate = {
    ...formDataUpdate,
    images: image.value,
  };

  console.log(dataUpdate);

  await axios
    .put(baseUrl + "/employees/" + id, dataUpdate)
    .then((res) => {
      console.log(res);
      isOpenModalUpdate.value = false;
      resetForm();
      fetchData();
      toast.success("Update successfully!");
    })
    .catch((err) => {
      console.log(err);
    });
};

const handleDelete = (id) => {
  Swal.fire({
    title: "Are you sure?",
    text: "You won't be able to revert this!",
    icon: "warning",
    showCancelButton: true,
    confirmButtonColor: "#3085d6",
    cancelButtonColor: "#d33",
    confirmButtonText: "Yes, delete it!",
  }).then((result) => {
    if (result.isConfirmed) {
      axios
        .delete(baseUrl + "/employees/" + id)
        .then(() => {
          Swal.fire({
            title: "Deleted!",
            text: "Your data has been deleted.",
            icon: "success",
          });
          fetchData();
        })
        .catch((err) => {
          console.log(err);
        });
    }
  });
};

onMounted(() => {
  fetchData();
});
</script>

<template>
  <div class="flex justify-center items-center">
    <div class="mt-5 w-4/6">
      <p class="text-center text-xl font-bold mb-5">Employee Management</p>

      <!-- Table -->
      <div class="flex justify-between">
        <!-- Input Search -->
        <div>
          <input
            type="text"
            placeholder="Search"
            class="placeholder:text-[#CCC] border border-[#ccc] pl-2 py-1 rounded-lg"
            v-model="searchValue"
            @change="handelSearch"
          />
        </div>
        <!-- Btn add -->
        <div
          @click="handleOpenModalAdd"
          class="inline-block rounded bg-green-600 px-4 py-2 text-xs font-medium text-white hover:bg-green-700 cursor-pointer"
        >
          Add +
        </div>
      </div>

      <div class="overflow-x-auto py-2">
        <table class="w-full divide-y-2 divide-gray-200 bg-white text-sm">
          <thead class="text-left">
            <tr>
              <th class="whitespace-nowrap px-4 py-2 font-medium text-gray-900">
                Name
              </th>
              <th class="whitespace-nowrap px-4 py-2 font-medium text-gray-900">
                Image
              </th>
              <th class="whitespace-nowrap px-4 py-2 font-medium text-gray-900">
                Birth Date
              </th>
              <th class="whitespace-nowrap px-4 py-2 font-medium text-gray-900">
                Status
              </th>
              <th class="whitespace-nowrap px-4 py-2 font-medium text-gray-900">
                Salary
              </th>
              <th class="px-4 py-2">Actions</th>
            </tr>
          </thead>

          <tbody class="divide-y divide-gray-200">
            <tr v-if="isLoading">
              <td>
                <Loading />
              </td>
            </tr>
            <EmployeeList
              v-for="data in filterEmploy"
              :key="data._id"
              :name="data.name"
              :images="data.images"
              :birthdate="data.birthdate"
              :status="data.status"
              :salary="data.salary"
            />
          </tbody>
        </table>
      </div>

      <!-- Modal add -->
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
                  This information will be displayed publicly so be careful what
                  you share.
                </p>

                <div
                  class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6"
                >
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

                <div
                  class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6"
                >
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

      <!-- Modal update -->
      <div
        v-if="isOpenModalUpdate"
        class="fixed overflow-y-auto bg-slate-600 inset-0 bg-opacity-50"
      >
        <div class="flex justify-center items-center">
          <form
            class="bg-white p-4"
            @submit.prevent="handleAUpdate(idEmployee)"
          >
            <div class="space-y-12">
              <div class="border-b border-gray-900/10 pb-12">
                <h2 class="text-base/7 font-semibold text-gray-900">
                  Profile Update
                </h2>
                <p class="mt-1 text-sm/6 text-gray-600">
                  This information will be displayed publicly so be careful what
                  you share.
                </p>

                <div
                  class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6"
                >
                  <div class="col-span-full">
                    <label
                      for="photo"
                      class="block text-sm/6 font-medium text-gray-900"
                      >Photo</label
                    >
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

                <div
                  class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6"
                >
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
                        v-model="formDataUpdate.name"
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
                        v-model="formDataUpdate.birthdate"
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
                        v-model="formDataUpdate.salary"
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
                        v-model="formDataUpdate.status"
                      />
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="mt-6 flex items-center justify-end gap-x-6">
              <button
                type="button"
                @click="handleCloseModalUpdate"
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
    </div>
  </div>
</template>
