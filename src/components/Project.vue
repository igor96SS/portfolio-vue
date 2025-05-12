<script setup>

defineProps({
  project: Object
});

</script>

<template>
  
  <section class="bg-blue-100 min-h-screen p-6">
    <div class="container mx-auto max-w-5xl px-12">
        
        <div class="bg-gray-900 p-6 rounded-lg shadow-md text-center md:text-left">
            
          <h1 class="text-3xl text-white font-bold">{{project.title}}</h1>
          <p class="text-gray-400 italic text-sm">{{project.course + " - " + project.year}}</p>
        </div>

        <div class="bg-white p-6 rounded-lg shadow-md ">
          <h3 class="text-amber-600 text-lg font-bold mb-4">
            Project Description
          </h3>

          <p class="mb-4">
            {{project.description}}
          </p>

          <h3 class="text-amber-600 text-lg font-bold mb-2">Technologies</h3>

          <div class="flex flex-wrap gap-2 mt-2">
            <span
              v-for="tech in project.technologies"
              :key="tech"
              class="px-3 py-1 bg-sky-200 text-gray-800 hover:bg-sky-400 hover:text-white rounded-full text-sm font-medium"
            >
              {{ tech }}
            </span>

          </div>
        </div>

    </div>
  </section>

</template>