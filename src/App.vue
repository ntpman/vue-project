<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <!-- Navbar -->
  <nav class="relative container mx-auto max-w-5xl py-6">
    <!-- Flex container -->
    <div class="flex items-center justify-between">
      <!-- Logo -->
      <h1 class="text-xl">Vue</h1>
      <!-- Menu Items -->
      <div class="hidden md:flex space-x-6">
        <RouterLink to="/" class="hover:text-red-500">Home</RouterLink>
        <RouterLink to="/skills" class="hover:text-red-500">Skills</RouterLink>
      </div>
      <!-- Button -->
      <RouterLink
        to="/skills/create"
        class="
          hidden
          md:block
          px-4
          py-2
          text-white
          bg-slate-800
          hover:text-red-500
          rounded-xl
        "
        >New Skill</RouterLink
      >
    </div>
  </nav>

  <RouterView />
</template>