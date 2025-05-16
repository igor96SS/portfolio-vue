<script setup>
import { ref } from 'vue'

const openSection = ref('personal')

const toggleSection = (section) => {
  openSection.value = openSection.value === section ? null : section
}
</script>

<template>
    
    <!-- PERSONAL INFORMATION-->
    <div class="bg-gray-300">
        <div class="mx-auto max-w-4xl px-9"> 
            <div class="border border-gray-300 dark:border-gray-700 rounded-lg mt-6">
                <button
                @click="toggleSection('personal')"
                class="w-full flex justify-between items-center p-4 text-lg font-medium bg-gray-100 dark:bg-gray-800 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700"
                >
                <div class="flex items-center gap-2 mb-4 ml-1">
                            <span>🌱</span>
                            <h2 class="text-sky-600 dark:text-sky-400 underline">Personal Life</h2>
                        </div>
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
        
                <div v-show="openSection === 'personal'" >
                    <section class="bg-gray-300 p-6">
                        <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 flex flex-col">
                            <ul class="list-disc text-white ml-7 ">
                                <li>
                                    <p class="text-sky-600 dark:text-white text-md mb-4">
                                        If you've made it this far, you probably already know my name — so let's skip that part!
                                    </p>
                                </li>
                                <li>
                                    <p class="text-gray-600 dark:text-white text-md mb-4">
                                        I'm from Portugal, more precisely from Figueira da Foz. In my free time, I enjoy cycling, learning guitar, watching movies, and going to the theatre.
                                    </p>
                                </li>
                                <li>
                                    <p class="text-gray-600 dark:text-white text-md mb-4">
                                        As a kid, I used to say I wanted to be a Computer Engineer — even though I had no idea what that meant. Turns out, I meant it after all.
                                    </p>
                                </li>
                                <li>
                                <p class="text-sky-600 dark:text-white text-md mb-2">
                                    The journey hasn't always been smooth, but in 2023, completing my Bachelor's Degree in Computer Engineering was a major personal achievement.
                                </p>
                                </li>
                            </ul>
                        </div>
                    </section>
                </div>
            </div>
        </div>
    </div>
    
    <!-- SCHOOL INFORMATION-->
    <div class="bg-blue-50 mt-6">
        <div class="mx-auto max-w-4xl px-9"> 
            <div class="mb-6 border border-gray-300 dark:border-gray-700 rounded-lg">
                <button
                @click="toggleSection('school')"
                class="w-full flex justify-between items-center p-4 text-lg font-medium bg-gray-100 dark:bg-gray-800 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700"
                >
                <div class="flex items-center gap-2 mb-4 ml-1">
                    <span>🏫</span>
                    <h2 class="text-sky-600 dark:text-sky-400 underline">Academic Life</h2>
                </div>
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
        
                <div v-show="openSection === 'school'" >
                    <section class="bg-blue-50 p-6">
                        <div class="container mx-auto max-w-4xl px-9">         
                            <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 flex flex-col">
                                
                                <ul class="list-disc text-white ml-7 ">
                                    <li>
                                        <p class="text-sky-600 dark:text-white text-md">
                                            High School - Management Informatics - 2016
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li>
                                                
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md">
                                            University - Professional Higher Technical Courses - 2017/2019
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li>
                                                
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md">
                                            University - Bachelor's Degree - 2019/2023
                                        </p>
                                        <ul class="list-[square] text-white ml-7">
                                            <li>
                                                
                                            </li>
                                        </ul>
                                    </li>
                                    
                                </ul>
                            </div>
                        </div>
                    </section>
                </div>
            </div>
        </div>
    </div>

    <!-- WORK INFORMATION-->
    <div class="bg-blue-50 mt-6">
        <div class="mx-auto max-w-4xl px-9"> 
            <div class="mb-6 border border-gray-300 dark:border-gray-700 rounded-lg">
                <button
                @click="toggleSection('work')"
                class="w-full flex justify-between items-center p-4 text-lg font-medium bg-gray-100 dark:bg-gray-800 dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700"
                >
                <div class="flex items-center gap-2 mb-4 ml-1">
                    <span>💼</span>
                    <h2 class="text-sky-600 dark:text-sky-400 underline">Professional Life</h2>
                </div>
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
        
                <div v-show="openSection === 'work'" >
                    <section class="bg-blue-50 p-6">
                        <div class="container mx-auto max-w-4xl px-9">         
                            <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 flex flex-col">
                                
                                <ul class="list-disc text-white ml-7 ">
                                    <li>
                                        <p class="text-sky-600 dark:text-white text-md">
                                            High School - Management Informatics - 2016
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li>
                                                
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md">
                                            University - Professional Higher Technical Courses - 2017/2019
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li>
                                                
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md">
                                            University - Bachelor's Degree - 2019/2023
                                        </p>
                                        <ul class="list-[square] text-white ml-7">
                                            <li>
                                                
                                            </li>
                                        </ul>
                                    </li>
                                    
                                </ul>
                            </div>
                        </div>
                    </section>
                </div>
            </div>
        </div>
    </div>

    

    


</template>