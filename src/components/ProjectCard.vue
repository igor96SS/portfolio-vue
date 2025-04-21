<script setup>
defineProps({
  id: String,
  title: String,
  description: String,
  technologies: String,
})
</script>

<template>
  <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 shadow-sm hover:shadow-md transition flex flex-col h-full">
    
    <!-- Content -->
    <div class="flex-grow">
      <h3 class="text-lg font-semibold text-gray-800 dark:text-white mb-1">{{ title }}</h3>
      <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">{{ description }}</p>
      <div class="border border-gray-100 mb-2"></div>
      <p class="text-gray-600 dark:text-gray-400 text-sm">{{ technologies }}</p>
    </div>

    <!-- Footer-style button -->
    <div class="mt-auto pt-3">
      <RouterLink
        :to="'/projects/' + id"
        class="inline-block bg-blue-300 hover:bg-blue-500 text-white px-4 py-2 rounded-lg text-sm"
      >
        Read More
      </RouterLink>
    </div>

  </div>
</template>