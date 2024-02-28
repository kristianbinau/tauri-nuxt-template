<template>
  <div class="flex flex-col justify-center items-start w-full h-screen">
    <h1 class="text-4xl font-bold">
      Hello, <span class="text-[#00DC82]">Nuxt</span> &
      <span
        class="bg-gradient-to-r from-[#67d6ed] to-[#FFC131] text-transparent bg-clip-text"
        >Tauri</span
      >!
    </h1>
    <p class="text-lg text-gray-500 mb-6">
      This is a starter template for building cross-platform desktop
      applications with Nuxt and Tauri.
    </p>

    <p class="text-lg text-gray-500 mb-6">
      Below is a Vue component that uses Tauri's invoke API to send a command to the Tauri backend. The backend then sends a response back to the frontend, which is displayed as a toast notification.
    </p>

    <Greet></Greet>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
</script>
