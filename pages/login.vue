<script setup>
import axios from "axios";
import { Form, Field, ErrorMessage } from "vee-validate";
import { toast } from "vue3-toastify";
import * as yup from "yup";
import baseUrl from "~/configs/baseUrl";
import Cookies from "js-cookie";

const validate = yup.object({
  email: yup.string().email("Email is not valid").required("* Required"),
  password: yup.string().required("* Required").min(6, "* Password need 6 char"),
});

const handleLogin = async (values) => {
  console.log(values);

  axios
    .post(baseUrl + "/auth/login", values)
    .then((res) => {
      console.log(res);
      const data = res.data;
      toast.success("Login successfully!");

      // localStorage.setItem("access_token", res.data.accessToken);
      Cookies.set("access_token", data.accessToken, {
        expires: 1,
        secure: process.env.NODE_ENV === "production",
        path: "/",
        sameSite: "Strict",
        httpOnly: true,
      });

      Cookies.set("userId", data.userInfo.userId, {
        expires: 1,
        secure: process.env.NODE_ENV === "production",
        path: "/",
        sameSite: "Strict",
      });
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
      <h2 class="text-2xl font-semibold text-center mb-6">Login</h2>

      <!-- Form Start -->
      <Form @submit="handleLogin" :validation-schema="validate">
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
          <ErrorMessage name="email" class="mt-1 text-red-500" />
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
          <ErrorMessage name="password" class="mt-1 text-red-500" />
        </div>

        <!-- Submit Button -->
        <div class="mt-6">
          <button
            type="submit"
            class="w-full py-2 px-4 bg-indigo-600 text-white rounded-md hover:bg-indigo-500 focus:ring-2 focus:ring-indigo-600 focus:outline-none"
          >
            Login
          </button>
        </div>
      </Form>

      <!-- Login Link -->
      <div class="mt-4 text-center text-sm text-gray-600">
        No account yet.
        <NuxtLink to="/register" class="text-indigo-600 hover:underline"
          >Register</NuxtLink
        >
      </div>
    </div>
  </div>
</template>
