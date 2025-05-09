<script setup>
import { useRoute } from 'vue-router';
import SchoolProjects from '@/assets/data/school_projects.json'
import PersonalProjects from '@/assets/data/personal_projects.json'
import WorkProjects from '@/assets/data/work_projects.json'
import { computed } from 'vue';
import BackButton from './BackButton.vue';

const route = useRoute();
const projectID = route.params.id;
const projects = [SchoolProjects, PersonalProjects, WorkProjects].flat();

const project = computed(()=> projects.find(p => p.id === projectID));

</script>

<template>
    <BackButton/>
    <section class="bg-blue-500 min-h-screen p-6">
        <div class="container m-auto py-10 px-6">
            <div class="grid grid-cols-1 md:grid-cols-70/30 w-full gap-6">
                <main>
            <div
              class="bg-gray-900 p-6 rounded-lg shadow-md text-center md:text-left"
            >
            <div
                class="text-gray-500 mb-4 flex align-middle justify-center md:justify-start"
              >
                <i
                  class="pi pi-map-marker text-lg text-orange-700 mr-2"
                ></i>
                <p class="text-orange-700">{{project.course + " - " + project.year}}</p>
              </div>


              <h1 class="text-3xl text-white font-bold mb-4">{{project.title}}</h1>
              
            </div>

            <div class="bg-white p-6 rounded-lg shadow-md mt-6">
              <h3 class="text-green-800 text-lg font-bold mb-6">
                Project Description
              </h3>

              <p class="mb-4">
                {{project.description}}
              </p>

              <h3 class="text-green-800 text-lg font-bold mb-2">Technologies</h3>

              <div class="flex flex-wrap gap-2 mt-2">
                <span
                  v-for="tech in project.technologies"
                  :key="tech"
                  class="px-3 py-1 bg-gray-100 text-gray-800 rounded-full text-sm font-medium"
                >
                  {{ tech }}
                </span>

              </div>
            </div>
          </main>
            </div>
        </div>
    </section>

</template>