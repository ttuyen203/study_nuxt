<script setup>
import { Form, Field, ErrorMessage } from "vee-validate";
import * as yup from "yup";
import baseUrl from "~/configs/baseUrl";
import { toast } from "vue3-toastify";
import axios from "axios";

const validate = yup.object({
  username: yup.string().required("Required").min(6, "Name need 6 char"),
  email: yup.string().required("Required").email("Email not ivalid"),
  password: yup.string().required("Required").min(6, "Password need 6 char"),
});

const onSubmit = async (values) => {
  console.log(values);

  axios
    .post(baseUrl + "/auth/register", values)
    .then((res) => {
      console.log(res);
      // navigateTo("/login");
      toast.success("Register successfully. Login now!");
    })
    .catch((err) => {
      console.log(err);
      toast.error(err.response.data.message);
    });
};
</script>

<template>
  <div class="flex justify-center items-center min-h-screen bg-gray-100">
    <div class="w-full max-w-md p-8 bg-white shadow-lg rounded-lg">
      <h2 class="text-2xl font-semibold text-center mb-6">Create an Account</h2>

      <!-- Form Start -->
      <Form @submit="onSubmit" :validation-schema="validate">
        <!-- Username -->
        <div class="mb-4">
          <label for="username" class="block text-sm font-medium text-gray-700">
            Username
          </label>
          <Field
            id="username"
            name="username"
            type="text"
            class="mt-1 p-2 w-full border rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500"
            placeholder="Enter your username"
          />
          <ErrorMessage name="username" class="text-red-500 mt-1" />
        </div>

        <!-- Email -->
        <div class="mb-4">
          <label for="email" class="block text-sm font-medium text-gray-700">
            Email
          </label>
          <Field
            id="email"
            name="email"
            type="email"
            class="mt-1 p-2 w-full border rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500"
            placeholder="Enter your email"
          />
          <ErrorMessage name="email" class="text-red-500 mt-1" />
        </div>

        <!-- Password -->
        <div class="mb-4">
          <label for="password" class="block text-sm font-medium text-gray-700">
            Password
          </label>
          <Field
            id="password"
            name="password"
            type="password"
            class="mt-1 p-2 w-full border rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500"
            placeholder="Enter your password"
          />
          <ErrorMessage name="password" class="text-red-500 mt-1" />
        </div>

        <!-- Submit Button -->
        <div class="mt-6">
          <button
            type="submit"
            class="w-full py-2 px-4 bg-indigo-600 text-white rounded-md hover:bg-indigo-500 focus:ring-2 focus:ring-indigo-600 focus:outline-none"
          >
            Register
          </button>
        </div>
      </Form>

      <!-- Login Link -->
      <div class="mt-4 text-center text-sm text-gray-600">
        Already have an account?
        <NuxtLink to="/login" class="text-indigo-600 hover:underline"
          >Login</NuxtLink
        >
      </div>
    </div>
  </div>
</template>
