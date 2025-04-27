<script setup>
import { computed } from 'vue';

// Defina as props diretamente
const props = defineProps({
  project: Object
});

// Computed property para formatar o array de tecnologias
const formattedTechnologies = computed(() => {
  return props.project.technologies.join(', '); // Verifica se existe a propriedade 'technologies'
});
</script>



<template>
  <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 shadow-sm hover:shadow-md transition flex flex-col h-full">
    
    <!-- Content -->
    <div class="flex-grow">
      <h3 class="text-lg font-semibold text-gray-800 dark:text-white mb-1">{{ project.title }}</h3>
      <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">{{ project.shortDescription }}</p>
      <div class="border border-gray-100 mb-2"></div>
      <p class="text-gray-600 dark:text-gray-400 text-sm">{{ formattedTechnologies }}</p>
    </div>

    <!-- Footer-style button -->
    <div class="mt-auto pt-3">
      <RouterLink
        :to="'/projects/' + project.id"
        class="inline-block bg-blue-300 hover:bg-blue-500 text-white px-4 py-2 rounded-lg text-sm"
      >
        Read More
      </RouterLink>
    </div>

  </div>
</template>