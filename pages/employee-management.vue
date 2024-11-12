<script setup>
import axios from "axios";
import Swal from "sweetalert2";
import { toast } from "vue3-toastify";
import EmployeeAdd from "~/components/Employees/EmployeeAdd.vue";
import EmployeeList from "~/components/Employees/EmployeeList.vue";
import EmployeeUpdate from "~/components/Employees/EmployeeUpdate.vue";
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

const handleUpdate = async (id) => {
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
  console.log(id);

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
            <!-- List data -->
            <EmployeeList
              v-for="data in filterEmploy"
              :key="data._id"
              :_id="data._id"
              :name="data.name"
              :images="data.images"
              :birthdate="data.birthdate"
              :status="data.status"
              :salary="data.salary"
              :handleOpenModalUpdate="handleOpenModalUpdate"
              :handleDelete="handleDelete"
            />
          </tbody>
        </table>
      </div>

      <!-- Modal add -->
      <EmployeeAdd
        :isOpenModalAdd="isOpenModalAdd"
        :handleAdd="handleAdd"
        :isLoadingImage="isLoadingImage"
        :image="image"
        :handleChangeImage="handleChangeImage"
        :formData="formData"
        :handleCloseModalAdd="handleCloseModalAdd"
      />

      <!-- Modal update -->
      <EmployeeUpdate
        :isOpenModalUpdate="isOpenModalUpdate"
        :handleUpdate="handleUpdate"
        :idEmployee="idEmployee"
        :image="image"
        :handleChangeImage="handleChangeImage"
        :formDataUpdate="formDataUpdate"
        :handleCloseModalUpdate="handleCloseModalUpdate"
      />
    </div>
  </div>
</template>
