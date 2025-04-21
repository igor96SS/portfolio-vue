<script setup>
import ProjectCard from './ProjectCard.vue'
import { ref } from 'vue'

// Toggle which section is open
const openSection = ref(null)

const toggleSection = (section) => {
  openSection.value = openSection.value === section ? null : section
}

// Dummy data for now
const schoolProjects = [
  { title: 'Math seen', description: 'Interactive plots using Vue and Chart.js', technologies: '', year: '', course: 'licenciatura'},
  { title: 'Student Portal Clone', description: 'Replicated our school portal UI with Vue', technologies: '', year:'', course: 'licenciatura' },
]

const workProjects = [
  { id: 'W1', title: 'Company Dashboard', description: '', technologies: '' },
  { id: 'W2', title: 'PoS Android Application', description: '', technologies: '' },
]

const personalProjects = [
  { id: 'P1', title: 'Cálculo Sinais', description: 'Android Application for industrial ', technologies: 'Java; kotlin; Android Studio' },
  { id: 'P2', title: 'Movies And Series', description: 'Personal Website to display a list of movies and series', technologies: '.NET Core WEB API; .NET Core Razor Pages; Microsoft SQL Server; C#' },
]
</script>

<template>
    <div class="max-w-4xl mx-auto py-10 px-4">
      
      <!-- SCHOOL PROJECTS -->
      <div class="mb-6 border border-gray-300 dark:border-gray-700 rounded-lg">
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
  
        <div v-show="openSection === 'school'" class="p-4 grid grid-cols-1 sm:grid-cols-2 gap-4">
          <ProjectCard
            v-for="(project, i) in schoolProjects"
            :key="`s${i}`"
            :id="`s${i}`"
            :title="project.title"
            :description="project.description"
            :technologies="project.technologies"
          />
        </div>
      </div>
  
      <!-- WORK PROJECTS -->
      <div class="mb-6 border border-gray-300 dark:border-gray-700 rounded-lg">
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
  
        <div v-show="openSection === 'work'" class="p-4 grid grid-cols-1 sm:grid-cols-2 gap-4">
          <ProjectCard
            v-for="(project, i) in workProjects"
            :key="`w${i}`"
            :id="`w${i}`"
            :title="project.title"
            :description="project.description"
            :technologies="project.technologies"
          />
        </div>
      </div>

      <!-- Personal PROJECTS -->
      <div class="border border-gray-300 dark:border-gray-700 rounded-lg">
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
            v-for="(project, i) in personalProjects"
            :key="`p${i}`"
            :id="`p${i}`"
            :title="project.title"
            :description="project.description"
            :technologies="project.technologies"
          />
        </div>
      </div>
      
    </div>
</template>
  