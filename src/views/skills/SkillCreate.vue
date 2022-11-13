<script setup>
import useSkills from "../../composables/skills";
import { reactive } from "vue";

const { storeSkill, errors } = useSkills();

const form = reactive({
  name: "",
  slug: "",
});
</script>

<template>
  <div class="container mx-auto max-w-sm bg-green-200 p-4 rounded-lg">
    <form @submit.prevent="storeSkill(form)">
      <div class="mb-6">
        <label for="name" class="block mb-2 text-sm font-medium"
          >Your name</label
        >
        <input
          v-model="form.name"
          type="text"
          id="name"
          class="
            bg-slate-50
            text-sm
            rounded-lg
            dark:bg-gray-700
            block
            w-full
            p-2.5
          "
          placeholder=""
        />
        <p
          v-if="errors.name"
          class="mt-2 text-sm text-red-600 dark:text-red-500"
        >
          <span class="font-medium">{{ errors.name[0] }}</span>
        </p>
      </div>
      <div class="mb-6">
        <label for="slug" class="block mb-2 text-sm font-medium"
          >Your slug</label
        >
        <input
          v-model="form.slug"
          type="text"
          id="slug"
          class="
            bg-slate-50
            text-sm
            rounded-lg
            dark:bg-gray-700
            block
            w-full
            p-2.5
          "
          placeholder=""
        />
        <p
          v-if="errors.slug"
          class="mt-2 text-sm text-red-600 dark:text-red-500"
        >
          <span class="font-medium">{{ errors.slug[0] }}</span>
        </p>
      </div>

      <button
        type="submit"
        class="
          p-3
          px-4
          py-2
          text-white
          bg-slate-800
          hover:text-red-500
          rounded-xl
        "
      >
        Store
      </button>
    </form>
  </div>
</template>