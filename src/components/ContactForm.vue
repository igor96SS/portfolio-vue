<script setup>

</script>

<template>
    <div class="flex justify-center bg-blue-50 p-6 pt-20 min-h-[100vh] pb-12">
        <div class="dark:bg-gray-900 shadow-lg rounded-2xl p-8 max-w-4xl w-full self-start">
            <div class="flex">
                <!-- Left Column -->
                <div class="flex-1 pr-8">
                    <form name="contact" method="POST" netlify data-netlify="true" class="space-y-4">
                        <input type="hidden" name="form-name" value="contact" />
                        <!-- NAME INPUT -->
                        <label for="name-label" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Your Name</label>
                        <div class="flex">
                            <span class="inline-flex items-center px-3 text-sm text-gray-900 bg-gray-200 border rounded-e-0 border-gray-300 border-e-0 rounded-s-md dark:bg-gray-600 dark:text-gray-400 dark:border-gray-600">
                            <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                <path d="M10 0a10 10 0 1 0 10 10A10.011 10.011 0 0 0 10 0Zm0 5a3 3 0 1 1 0 6 3 3 0 0 1 0-6Zm0 13a8.949 8.949 0 0 1-4.951-1.488A3.987 3.987 0 0 1 9 13h2a3.987 3.987 0 0 1 3.951 3.512A8.949 8.949 0 0 1 10 18Z"/>
                            </svg>
                            </span>
                            <input type="text" id="name" name="name" class="rounded-none rounded-e-lg bg-gray-50 border text-gray-900 focus:ring-blue-500 focus:border-blue-500 block flex-1 min-w-0 w-full text-sm border-gray-300 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Your Name">
                        </div>

                        <!-- EMAIL INPUT -->
                        <label for="email-label" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Your Email</label>
                        <div class="relative mb-6">
                            <div class="absolute inset-y-0 start-0 flex items-center ps-3.5 pointer-events-none">
                            <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 16">
                                <path d="m10.036 8.278 9.258-7.79A1.979 1.979 0 0 0 18 0H2A1.987 1.987 0 0 0 .641.541l9.395 7.737Z"/>
                                <path d="M11.241 9.817c-.36.275-.801.425-1.255.427-.428 0-.845-.138-1.187-.395L0 2.6V14a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V2.5l-8.759 7.317Z"/>
                            </svg>
                            </div>
                            <input type="text" id="email" name="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full ps-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="name@email.com">
                        </div>

                        <!-- MESSAGE INPUT -->
                        <label for="message-label" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Your Message</label>
                        <div class="relative mb-6">
                            <div class="absolute top-3 start-0 flex items-start ps-3.5 pointer-events-none">
                            <svg class="w-4 h-4 text-gray-500 mt-1 dark:text-gray-400" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M21 6h-18v12h18v-12zm0-2c1.104 0 2 .896 2 2v12c0 1.104-.896 2-2 2h-18c-1.104 0-2-.896-2-2v-12c0-1.104.896-2 2-2h18zm-9 9h-6v-2h6v2zm8-3h-14v-2h14v2z"/>
                            </svg>
                            </div>
                            <textarea id="message" name="message" rows="4" placeholder="Type your message here..." class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full ps-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500 resize-none"></textarea>
                        </div>

                        <!-- SEND BUTTON -->
                        <button type="submit" class="w-full flex items-center justify-center bg-blue-600 text-white py-2 px-4 rounded-lg hover:bg-blue-700 transition duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50">
                            Send
                        </button>
                    </form>
                </div>

                <!-- Right Column -->
                <div class="flex-1">
                    <h2 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Contact Me</h2>
                    <p class="text-gray-600 dark:text-gray-400 mb-6">You can contact me through this form or via my social profiles below.</p>

                    <!-- SOCIAL LINKS -->
                    <div class="pt-6 border-t border-gray-700 mt-6">
                        <h3 class="text-white text-sm font-semibold mb-4">Find me on</h3>
                        <div class="flex space-x-4">
                            <!-- GitHub -->
                            <a href="https://github.com/igor96SS" target="_blank" class="text-gray-400 hover:text-white transition">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                fill-rule="evenodd"
                                d="M12 0C5.372 0 0 5.373 0 12c0 5.303 3.438 9.8 8.207 11.387.6.111.793-.26.793-.577v-2.234c-3.338.726-4.033-1.61-4.033-1.61-.547-1.387-1.333-1.756-1.333-1.756-1.09-.745.083-.73.083-.73 1.205.084 1.838 1.237 1.838 1.237 1.07 1.834 2.807 1.304 3.492.997.108-.775.418-1.304.762-1.604-2.665-.304-5.467-1.334-5.467-5.931 0-1.31.469-2.381 1.236-3.221-.124-.303-.535-1.523.117-3.176 0 0 1.008-.323 3.301 1.23a11.52 11.52 0 0 1 3.005-.404 11.52 11.52 0 0 1 3.006.404c2.291-1.553 3.298-1.23 3.298-1.23.653 1.653.242 2.873.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.48 5.921.43.372.814 1.102.814 2.222v3.293c0 .32.192.694.8.576C20.565 21.796 24 17.3 24 12c0-6.627-5.373-12-12-12z"
                                clip-rule="evenodd"
                                />
                            </svg>
                            </a>

                            <!-- LinkedIn -->
                            <a href="https://www.linkedin.com/in/igor-simoes" target="_blank" class="text-gray-400 hover:text-white transition">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                d="M20.447 20.452H17.21v-5.569c0-1.328-.025-3.036-1.849-3.036-1.852 0-2.135 1.445-2.135 2.939v5.666H9v-11.5h3.104v1.571h.044c.433-.82 1.493-1.683 3.074-1.683 3.29 0 3.895 2.165 3.895 4.978v6.634zM5.337 7.433a1.814 1.814 0 1 1 .002-3.628 1.814 1.814 0 0 1-.002 3.628zM6.813 20.452H3.861v-11.5h2.952v11.5zM22.225 0H1.771C.792 0 0 .771 0 1.726v20.547C0 23.23.792 24 1.771 24h20.451C23.205 24 24 23.23 24 22.274V1.726C24 .771 23.205 0 22.225 0z"
                                />
                            </svg>
                            </a>

                            <!-- Instagram -->
                            <a href="https://www.instagram.com/techiss96/" target="_blank" class="text-gray-400 hover:text-white transition">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path 
                                d="M7.0301.084c-1.2768.0602-2.1487.264-2.911.5634-.7888.3075-1.4575.72-2.1228 1.3877-.6652.6677-1.075 1.3368-1.3802 2.127-.2954.7638-.4956 1.6365-.552 2.914-.0564 1.2775-.0689 1.6882-.0626 4.947.0062 3.2586.0206 3.6671.0825 4.9473.061 1.2765.264 2.1482.5635 2.9107.308.7889.72 1.4573 1.388 2.1228.6679.6655 1.3365 1.0743 2.1285 1.38.7632.295 1.6361.4961 2.9134.552 1.2773.056 1.6884.069 4.9462.0627 3.2578-.0062 3.668-.0207 4.9478-.0814 1.28-.0607 2.147-.2652 2.9098-.5633.7889-.3086 1.4578-.72 2.1228-1.3881.665-.6682 1.0745-1.3378 1.3795-2.1284.2957-.7632.4966-1.636.552-2.9124.056-1.2809.0692-1.6898.063-4.948-.0063-3.2583-.021-3.6668-.0817-4.9465-.0607-1.2797-.264-2.1487-.5633-2.9117-.3084-.7889-.72-1.4568-1.3876-2.1228C21.2982 1.33 20.628.9208 19.8378.6165 19.074.321 18.2017.1197 16.9244.0645 15.6471.0093 15.236-.005 11.977.0014 8.718.0076 8.31.0215 7.0301.0839m.1402 21.6932c-1.17-.0509-1.8053-.2453-2.2287-.408-.5606-.216-.96-.4771-1.3819-.895-.422-.4178-.6811-.8186-.9-1.378-.1644-.4234-.3624-1.058-.4171-2.228-.0595-1.2645-.072-1.6442-.079-4.848-.007-3.2037.0053-3.583.0607-4.848.05-1.169.2456-1.805.408-2.2282.216-.5613.4762-.96.895-1.3816.4188-.4217.8184-.6814 1.3783-.9003.423-.1651 1.0575-.3614 2.227-.4171 1.2655-.06 1.6447-.072 4.848-.079 3.2033-.007 3.5835.005 4.8495.0608 1.169.0508 1.8053.2445 2.228.408.5608.216.96.4754 1.3816.895.4217.4194.6816.8176.9005 1.3787.1653.4217.3617 1.056.4169 2.2263.0602 1.2655.0739 1.645.0796 4.848.0058 3.203-.0055 3.5834-.061 4.848-.051 1.17-.245 1.8055-.408 2.2294-.216.5604-.4763.96-.8954 1.3814-.419.4215-.8181.6811-1.3783.9-.4224.1649-1.0577.3617-2.2262.4174-1.2656.0595-1.6448.072-4.8493.079-3.2045.007-3.5825-.006-4.848-.0608M16.953 5.5864A1.44 1.44 0 1 0 18.39 4.144a1.44 1.44 0 0 0-1.437 1.4424M5.8385 12.012c.0067 3.4032 2.7706 6.1557 6.173 6.1493 3.4026-.0065 6.157-2.7701 6.1506-6.1733-.0065-3.4032-2.771-6.1565-6.174-6.1498-3.403.0067-6.156 2.771-6.1496 6.1738M8 12.0077a4 4 0 1 1 4.008 3.9921A3.9996 3.9996 0 0 1 8 12.0077"
                                />
                            </svg>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>