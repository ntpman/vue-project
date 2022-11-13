<script setup>
import useSkills from "../../composables/skills";
import { onMounted } from "vue";

const { skills, getSkills, destroySkill } = useSkills();

onMounted(() => getSkills());
</script>

<template>
  <div class="container mx-auto max-w-5xl">
    <div class="overflow-x-auto relative shadow-md sm:rounded-lg">
      <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
        <thead
          class="
            text-xs text-gray-700
            uppercase
            bg-gray-50
            dark:bg-gray-700 dark:text-gray-400
          "
        >
          <tr>
            <th scope="col" class="py-3 px-6">Name</th>
            <th scope="col" class="py-3 px-6">Slug</th>
            <th scope="col" class="py-3 px-6">
              <span class="sr-only">Edit</span>
            </th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="skill in skills"
            :key="skill.id"
            class="
              bg-white
              border-b
              dark:bg-gray-800 dark:border-gray-700
              hover:bg-gray-50
              dark:hover:bg-gray-600
            "
          >
            <td class="py-4 px-6">{{ skill.name }}</td>
            <td class="py-4 px-6">{{ skill.slug }}</td>
            <td class="py-4 px-6 text-right">
              <RouterLink
                :to="{ name: 'SkillEdit', params: { id: skill.id } }"
                class="
                  font-medium
                  text-blue-600
                  dark:text-blue-500
                  hover:text-blue-900
                  mx-2
                "
              >
                แก้ไข</RouterLink
              >
              <span
                @click="destroySkill(skill.id)"
                href=""
                class="
                  font-medium
                  text-red-600
                  dark:text-red-500
                  hover:text-red-900
                  mx-2
                  cursor-pointer
                "
              >
                ลบ</span
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>