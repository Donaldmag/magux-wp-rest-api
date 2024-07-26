<template>
    <div>
        <header class="text-gray-600 dark:text-white body-font bg-white dark:bg-transparent">
            <div class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center relative shadow shadow-slate-200 dark:shadow-none">

                <a class="flex title-font font-medium items-center  dark:text-white-gray-900 dark:text-white mb-4 md:mb-0">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-linecap="round"
                        stroke-linejoin="round" stroke-width="2"
                        class="w-10 h-10 text-white p-2 bg-indigo-500 rounded-full" viewBox="0 0 24 24">
                        <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path>
                    </svg>
                    <span class="ml-3 text-xl">MagU/X</span>
                </a>

                <nav
                    class="md:mr-auto md:ml-4 md:py-1 md:pl-4 md:border-l md:border-gray-400	flex flex-wrap items-center text-base justify-center">
                    <a href="javascript:void(0);" class="mr-5 hover:text-gray-900 dark:text-white">Components</a>
                    <a href="javascript:void(0);" class="mr-5 hover:text-gray-900 dark:text-white">Templates</a>
                    <a href="javascript:void(0);" class="mr-5 hover:text-gray-900 dark:text-white">About Me</a>
                </nav>

                <button class="inline-flex items-center bg-blue-500 border-0 py-1 px-3 focus:outline-none hover:opacity-80 rounded-full text-base text-white font-semibold mt-4 md:mt-0">Order a Template
                </button>
                <span @click="toggleDarkMode" class="p-1 mx-2 rounded-full cursor-pointer" :class="isDark ? 'bg-[#f3f4f626]' : 'bg-gray-100'">
                    <svg :class="{ 'hidden' : isDark === true}" class="text-gray-600 dark:text-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="true" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M20.354 15.354A9 9 0 0 1 8.646 3.646A9.003 9.003 0 0 0 12 21a9.003 9.003 0 0 0 8.354-5.646"/></svg>
                    <svg :class="{ 'hidden' : isDark === false}" class="dark:text-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="true" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 1 1-8 0a4 4 0 0 1 8 0"/></svg>
                </span>
                

                <!-- Search -->
                <div class="w-[420px] absolute right-[50%] left-[50%] -translate-x-[50%] shadow-b shadow-slate-200">
                    <!-- component -->
                    <div class='flex items-center justify-center'>
                        <div class="flex rounded-full bg-gray-200 group px-2 py-0.5 w-full max-w-[600px]">
                            <input
                                type="text"
                                class="w-full placeholder:text-slate-400 group-focus:bg-white border-none focus:border-none focus:ring-0 rounded-xl flex bg-transparent pl-2 text-slate-600 text-sm outline-0 focus:outline-none"
                                placeholder="Search for a component name"
                            />
                            <button type="submit" class="relative p-1 rounded-full dark:text-gray-600">
                                <svg xmlns="http://www.w3.org/2000/svg" class="bg-transparent" width="24" height="24" viewBox="0 0 24 24"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="m21 21l-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"/></svg>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </header>
    </div>
</template>

<script setup>
import { useDark, useToggle } from "@vueuse/core";
const isDark = useDark({
    // attribute: "theme", // attribute name
    valueDark: "dark", // attribute value for dark mode
    // valueLight: "custom-light",
});

function toggleDarkMode() {
    isDark.value = !isDark.value
}
</script>