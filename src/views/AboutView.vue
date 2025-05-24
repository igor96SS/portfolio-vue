<script setup>
import { ref } from 'vue'

const openSection = ref('personal')

const toggleSection = (section) => {
  openSection.value = openSection.value === section ? null : section
}
</script>

<template>
    <div class="bg-blue-50 min-h-screen p-6 " >

    
    <!-- PERSONAL INFORMATION-->
    <div class="">
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
    <div class="mt-6">
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
                    <section class="bg-gray-300 p-6">
                        <div class="container mx-auto max-w-4xl px-9">         
                            <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 flex flex-col">
                                
                                <ul class="list-disc text-white ml-7 ">
                                    <li>
                                        <p class="text-sky-600 dark:text-white text-md underline">
                                            High School - Management Informatics - 2016
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li class="mt-3">
                                                In high school was where I had my first contact with programming and SQL databases!
                                            </li>
                                            <li class="mt-3">
                                                I also completed an internship where I worked with hardware, focusing on fixing and upgrading computers.
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md underline">
                                            Professional Higher Technical Course - Information Systems Programming - 2017/2019
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li class="mt-3">
                                                Before my Bachelor's degree, I completed a two-year course where I had the opportunity to explore different programming 
                                                languages and work on challenging projects.
                                            </li>
                                            <li class="mt-3">
                                                As part of this course, I also completed an internship, which was an incredibly valuable experience. 
                                                <br>
                                                I had the chance to work on exciting projects using technologies I hadn't worked with before, which tested my 
                                                adaptability and helped me grow both technically and personally.
                                            </li>
                                            <li class="mt-3">
                                                All these experiences had me wanting to learn more, which led me to the decision to pursue a degree in Computer Engineering.
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md underline">
                                            Bachelor's Degree - Computer Engineering (Information Systems) - 2019/2023
                                        </p>
                                        <ul class="list-[square] text-white ml-7">
                                            <li class="mt-3">
                                                Tough four-years of learning. So much knowledge to absorb and so little size in the SSD 😅
                                            </li>
                                            <li class="mt-3">
                                                It was challenging, fulfilling, and so much more than I could have ever anticipated. 
                                                <br> I definitely became a different person — with a much more creative mindset and a greater openness to challenges.
                                            </li>
                                            <li class="mt-3">
                                                Reaching this milestone was a major personal accomplishment and marked the end of an important phase in my life.
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
    <div class="mt-6">
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
                    <section class="bg-gray-300 p-6">
                        <div class="container mx-auto max-w-4xl px-9">         
                            <div class="bg-white dark:bg-gray-900 border border-gray-200 dark:border-gray-700 rounded-xl p-4 flex flex-col">
                                
                                <ul class="list-disc text-white ml-7 ">
                                   <li>
                                        <p class="text-sky-600 dark:text-white text-md underline">
                                            Internship - Software Development - 2019
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li class="mt-3">
                                                Refactor of an API using the framework Lumen/Laravel
                                            </li>
                                            <li class="mt-3">
                                                PoS Android Application using Kotlin and objectBox (NoSQL database).
                                                <br> This application was able to print receipts through bluetooth connection to a thermal printer.
                                            </li>
                                            <li class="mt-3">
                                                CRM website using React.js, Rest API with framework Lumen/Laravel and Microsoft SQL Server for the database.
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md underline">
                                            Freelancer - Full-Stack project - 2024/2025
                                        </p>
                                        <ul class="list-[square] text-white ml-7 mb-3">
                                            <li class="mt-3">
                                               Website to manage information about equipments + statistics using ASP.NET Core Razor Pages, ASP.NET Core Web API, Microsoft SQL Server and IIS web server
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <p class="text-gray-600 dark:text-white text-md underline">
                                            Junior Graduate Malware Analyst - 2024
                                        </p>
                                        <ul class="list-[square] text-white ml-7">
                                            <li class="mt-3">
                                                An opportunity to learn about cybersecurity and reverse engineering of Android applications, where I learned amazing techniques 
                                                in a field I knew very little about — but one that I'm definitely eager to explore further.
                                            </li>
                                            <li class="mt-3">
                                                Static and Dynamic Analysis of Android applications
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

    
</div>
    


</template>