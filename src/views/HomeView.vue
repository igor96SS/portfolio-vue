<script setup>
import { onMounted, ref } from 'vue'

const introSection = ref(null)

onMounted(() => {
  setTimeout(() => {
    introSection.value.classList.remove('opacity-0', 'translate-y-10')
    introSection.value.classList.add('opacity-100', 'translate-y-0')
  }, 100) // short delay for better feeling
})
</script>

<template>
    <section class=" dark:bg-gray-900 py-20 mb-4">
      <div
        class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center"
      >
        <div class="text-center">
          <h1
            class="text-4xl font-extrabold text-white sm:text-5xl md:text-6xl"
          >
          { \ } Still in Development { / }
          </h1>
        </div>
      </div>
    </section>
    <section
        class="intro text-center py-16 opacity-0 translate-y-10 transition-all duration-1000 ease-out" ref="introSection">
        <h1 class="text-4xl font-bold mb-4">Welcome to my portfolio!</h1>
        <p class="text-lg text-gray-600">Life in software development</p>
        <RouterLink
        to="/projects"
        class="mt-6 inline-block bg-blue-500 hover:bg-blue-600 text-white px-6 py-3 rounded-lg transition"
        >
        View all Projects
        </RouterLink>
    </section>

     <!-- New "Looking for a Job" Section -->
    <section class="bg-blue-100 py-16 text-center">
        <h2 class="text-3xl font-bold mb-4">I'm currently looking for new opportunities!</h2>
        <p class="text-lg text-gray-600 mb-6">If you have an exciting project or opportunity, feel free to reach out.</p>
        <RouterLink
        to="/contact"
        class="inline-block bg-slate-700 hover:bg-slate-800 text-white px-6 py-3 rounded-lg transition"
        >
        Contact Me
        </RouterLink>
    </section>
    
</template>