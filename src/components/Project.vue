<script setup>
import { ref } from 'vue';


const props = defineProps({
  project: Object
});


const currentIndex = ref(0);

const prev = () => {
  currentIndex.value = currentIndex.value - 1;
  if(currentIndex.value<0){
    currentIndex.value=props.project.images.length-1;
  }
};

const next = () => {
  currentIndex.value = currentIndex.value + 1;
  if(currentIndex.value==props.project.images.length){
    currentIndex.value=0;
  }
}


</script>

<template>
  
  <section class="bg-blue-100  p-6">
    <div class="container mx-auto max-w-5xl px-12">
        
        <div class="bg-gray-900 p-6 rounded-lg shadow-md text-center md:text-left">
            
          <h1 class="text-3xl text-white font-bold">{{project.title}}</h1>
          <p v-if="project.course" class="text-gray-400 italic text-sm">
            {{ project.course + " - " + project.year }}
          </p>
          <p v-else class="text-gray-400 italic text-sm">
            {{ project.year }}
          </p>

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

  <section v-if="project.images && project.images.length" class="max-w-4xl mx-auto py-8">
    <!-- Main Image -->
    <div class="relative">
      <img
        :src="project.images[currentIndex]"
        class="w-full h-96 object-contain rounded-2xl shadow-lg"
        :alt="`Imagem ${currentIndex + 1}`"
      />

      <!-- Navigation buttons -->
      <button
        @click="prev"
        class="absolute top-1/2 left-2 -translate-y-1/2 bg-white p-2 rounded-full shadow hover:bg-gray-100"
      >
        ◀
      </button>
      <button
        @click="next"
        class="absolute top-1/2 right-2 -translate-y-1/2 bg-white p-2 rounded-full shadow hover:bg-gray-100"
      >
        ▶
      </button>
    </div>

    <!-- Miniatures -->
    <div class="flex gap-2 mt-4 overflow-x-auto">
      <img
        v-for="(img, index) in project.images"
        :key="index"
        :src="img"
        @click="currentIndex = index"
        :class="[
          'h-20 w-32 object-cover rounded cursor-pointer transition',
          index === currentIndex ? 'ring-4 ring-blue-500' : 'opacity-70 hover:opacity-100'
        ]"
        :alt="`Miniature ${index + 1}`"
      />
    </div>
  </section>





</template>