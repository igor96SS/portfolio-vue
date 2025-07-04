<script setup>
import SchoolProjects from '@/assets/data/school_projects.json'
import PersonalProjects from '@/assets/data/personal_projects.json'
import WorkProjects from '@/assets/data/work_projects.json'

import ProjectCard from './ProjectCard.vue'
import { ref } from 'vue'

// Toggle which section is open
const openSection = ref('school')

const toggleSection = (section) => {
  openSection.value = openSection.value === section ? null : section
}

const schoolProjects = ref(SchoolProjects);
const workProjects = ref(WorkProjects);
const personalProjects = ref(PersonalProjects);

</script>

<template>
    <div class="max-w-5xl mx-auto py-10 px-4">
      <div class="flex mb-6 justify-center text-lg items-center space-x-2">
        <span class="text-4xl">⚠️</span>
        <span>Some Projects still incomplete</span>
        <span class="text-4xl">⚠️</span>
      </div>

      <!-- SCHOOL PROJECTS -->
      <div class="bg-gray-300 mb-6 border border-gray-300 dark:border-gray-700 rounded-lg">
        <button
          @click="toggleSection('school')"
          class="w-full flex justify-between items-center p-4 text-lg font-medium bg-gray-100 dark:bg-gray-800 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700"
        >
          <span>🎓 School Projects</span>
          <svg
            class="w-5 h-5 transition-transform"
            :class="{ 'rotate-180': openSection === 'school' }"
            fill="none"
            viewBox="0 0 24 24"
          >
            <path
              d="M19 9l-7 7-7-7"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </button>
  
        <div v-show="openSection === 'school'" class="p-4 grid grid-cols-1 sm:grid-cols-3 gap-4">
          <ProjectCard
            v-for="project in schoolProjects"
            :key="project.id"
            :project="project"
          />
        </div>
      </div>
  
      <!-- WORK PROJECTS -->
      <div class="bg-gray-300 mb-6 border border-gray-300 dark:border-gray-700 rounded-lg">
        <button
          @click="toggleSection('work')"
          class="w-full flex justify-between items-center p-4 text-lg font-medium bg-gray-100 dark:bg-gray-800 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700"
        >
          <span>💼 Work Projects</span>
          <svg
            class="w-5 h-5 transition-transform"
            :class="{ 'rotate-180': openSection === 'work' }"
            fill="none"
            viewBox="0 0 24 24"
          >
            <path
              d="M19 9l-7 7-7-7"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </button>
  
        <div v-show="openSection === 'work'" class="p-4 grid grid-cols-1 sm:grid-cols-3 gap-4">
          <ProjectCard
            v-for="project in workProjects.slice(0,workProjects.length-2)"
            :key="project.id"
            :project="project"
          />
        </div>
      </div>

      <!-- Personal PROJECTS -->
      <div class="bg-gray-300 border border-gray-300 dark:border-gray-700 rounded-lg">
        <button
          @click="toggleSection('personal')"
          class="w-full flex justify-between items-center p-4 text-lg font-medium bg-gray-100 dark:bg-gray-800 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700"
        >
          <span>💡 Personal Projects</span>
          <svg
            class="w-5 h-5 transition-transform"
            :class="{ 'rotate-180': openSection === 'personal' }"
            fill="none"
            viewBox="0 0 24 24"
          >
            <path
              d="M19 9l-7 7-7-7"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </button>
  
        <div v-show="openSection === 'personal'" class="p-4 grid grid-cols-1 sm:grid-cols-2 gap-4">
          <ProjectCard
            v-for="project in personalProjects"
            :key="project.id"
            :project="project"
          />
        </div>
      </div>
      
    </div>
</template>