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

const isModalOpen = ref(false)
const modalImage = ref(null)

function openModal(image) {
  modalImage.value = image
  isModalOpen.value = true
}

function closeModal() {
  isModalOpen.value = false
  modalImage.value = null
}

</script>



<template v-if="isModalOpen">
  
  <section class="bg-gray-300 p-6">
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

          <p class="mb-4" >
            {{project.description}}
          </p>

          <p class="mb-4" v-if="project.description2">
            {{project.description2}}
            <a :href="project.url" target="_blank" rel="noopener noreferrer" class="text-blue-500 hover:underline">
              {{project.urlTitle}}
            </a>
          </p>

          <p class="mb-4" v-if="project.description3">
            {{project.description3}}
            <a v-if="project.url1" :href="project.url1" target="_blank" rel="noopener noreferrer" class="text-blue-500 hover:underline">
              {{project.url1Title}}
            </a>
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

  <section v-if="project.images && project.images.length" class="bg-blue-100 mx-auto py-5">

    <div class="container mx-auto max-w-5xl px-12">
      <!-- Main Media -->
      <div class="relative bg-white">
        <template v-if="!project.images[currentIndex].endsWith('.mp4')">
          <img
            :src="project.images[currentIndex]"
            class="w-full h-72 object-contain rounded-2xl shadow-lg"
            :alt="`Image ${currentIndex + 1}`"
            @click="openModal(project.images[currentIndex])"
          />
        </template>
        <template v-else>
          <video
            :src="project.images[currentIndex]"
            class="w-full h-72 object-contain rounded-2xl shadow-lg"
            controls
          ></video>
        </template>

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
      <div class="bg-white mt-4 px-2 overflow-x-auto">
        <div class="flex w-max gap-2">
          <div
            v-for="(src, index) in project.images"
            :key="index"
            @click="currentIndex = index"
            :class="[ 
              'h-20 w-32 rounded cursor-pointer overflow-hidden transition',
              index === currentIndex ? 'ring-4 ring-blue-500' : 'opacity-70 hover:opacity-100'
            ]"
          >
            <template v-if="!src.endsWith('.mp4')">
              <img
                :src="src"
                class="h-full w-full object-cover"
                :alt="`Miniature ${index + 1}`"
              />
            </template>
            <template v-else>
              <div class="relative h-full w-full bg-black flex items-center justify-center">
                <span class="text-white text-xl">▶</span>
              </div>
            </template>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div
    v-if="isModalOpen"
    class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-80"
    @click="closeModal"
  >
    <img
      :src="modalImage"
      class="max-w-full max-h-full rounded-lg shadow-xl"
      @click.stop
    />
  </div>

</template>