<template>
    <div class="bg-stone-800 m-2 rounded-md border-2 border-stone-600">
        <div class="flex justify-between">
            <h1 class="underline font-bold p-2 text-xl">{{ activeSection }}</h1>
            <ul class="flex bg-stone-700 items-center rounded-bl-md rounded-tr-md overflow-hidden">
                <li v-for="section in sections" :key="section" class="p-3" :class="getActiveClass(section)">
                    <button @click="setActiveSection(section)">{{ section }}</button>
                </li>
            </ul>
        </div>
        <div class="p-2 text-stone-400">
            <div v-if="activeSection == 'About'">
                <h1 class="mb-2">Experience</h1>
                <ol class="relative border-l-2 border-green-400">
                    <li class="mb-10 ml-4">
                        <time class="mb-1 text-sm leading-none text-green-400">JAN 2020 - JUNE 2023</time>
                        <h2><label class="font-bold">Software Developer</label>, Reynolds and Reynolds</h2>
                        <ul class="list-['-'] list-inside"> 
                            <li>Developed a large cloud-based CRM, using a variety of technologies both modern and legacy.</li>
                            <li>Worked to produce production code to regular development cycle deadlines.</li>
                            <li>Developed integrations with large automobile manufacturers.</li>
                            <li>Maintained and expanded the vehicle finance application to manage customer vehicle finance proposals.</li>
                            <li>Built an API to integrate with Apple Push Notification Service.</li>
                            <li>Investigated and produced fixes for various bugs.</li>
                            <li>Developed and managed large interconnected SQL server databases.</li>
                            <li>“Rookie Of the Year” winner.</li>
                            <li>2 time “Employee Of the Month” winner.</li>
                        </ul>
                    </li>
                    <li class="mb-10 ml-4">
                        <time class="mb-1 text-sm leading-none text-green-400">JUL 2015 - SEP 2015, SEP 2018 - MAY 2019</time>
                        <h2><label class="font-bold">Associate SAS programmer</label>, S-cubed Biometrics</h2>
                        <ul class="list-['-'] list-inside"> 
                            <li>Performed SAS programming for efficacy and safety tables, listings, figures and analyses.</li>
                            <li>Produced tables, listings and figures of data for reports (e.g. Clinical Study Reports, Statistical Reports, etc).</li>
                            <li>Performed QC of tables, figures and analyses.</li>
                            <li>Participated in meetings with colleagues on matters related to current and future projects.</li>
                            <li>Worked as part of a team in order to complete larger software development projects.</li>
                        </ul>
                    </li>
                    <li class="mb-10 ml-4">
                        <time class="mb-1 text-sm leading-none text-green-400">SEP 2017 - SEP 2018</time>
                        <h2><label class="font-bold">Customer Delivery Driver</label>, Tesco</h2>
                        <ul class="list-['-'] list-inside"> 
                            <li>Delivered goods to customers in a timely manner whilst ensuring product quality and accuracy.</li>
                            <li>Provided excellent customer service by addressing any concerns and resolving issues efficiently.</li>
                            <li>Maintaining quality of service under strong time pressures.</li>
                        </ul>
                    </li>
                </ol>
                <h1 class="mb-2">Education</h1>
                <ol class="relative border-l-2 border-green-400">
                    <li class="mb-10 ml-4">
                        <time class="mb-1 text-sm leading-none text-green-400">SEP 2014 - SEP 2017</time>
                        <h2><label class="font-bold">BSc Mathematics and Computer Science 2:1</label>, University of Birmingham</h2>
                    </li>
                    <li class="mb-10 ml-4">
                        <time class="mb-1 text-sm leading-none text-green-400">SEP 2012 - SEP 2014</time>
                        <h2><label class="font-bold">A Levels</label>, Lord Williams's School</h2>
                    </li>
                </ol>
            </div>
            <div v-if="activeSection == 'Projects'">
                Projects stuff
            </div>
            <div v-if="activeSection == 'Contact'">
                <div class="pb-4">
                    <svg class="h-10 w-10 text-green-500 fill-current  inline" xmlns="http://www.w3.org/2000/svg" shape-rendering="geometricPrecision" text-rendering="geometricPrecision" image-rendering="optimizeQuality" fill-rule="evenodd" clip-rule="evenodd" viewBox="0 0 465 512.28">
                        <path fill-rule="nonzero" d="m27.59 192.83 10.23 9.15V9.31c0-5.14 4.17-9.31 9.31-9.31h279.8a9.3 9.3 0 0 1 7.17 3.37l88.35 92.07c1.74 1.8 2.6 4.12 2.6 6.44l.02 101.57 12.74-11.13c2.67-2.34 5.64-3.37 8.73-3.37 2.59 0 5.06.78 7.34 2.14 1.68 1.01 3.25 2.37 4.63 3.95 3.64 4.16 6.32 10.57 6.32 15.87v272.66c.22 1.16.23 2.34 0 3.5v4.29c0 5.76-2.36 11-6.14 14.78-3.78 3.78-9.01 6.14-14.77 6.14H20.91c-5.75 0-10.99-2.36-14.77-6.14C2.36 502.36 0 497.12 0 491.36V210.91c0-5.4 2.77-11.93 6.47-16.08l.65-.65c1.24-1.29 2.59-2.4 3.98-3.21l.96-.49c1.96-.99 4.07-1.55 6.24-1.55 3.14 0 6.15 1.06 8.83 3.46l.46.44zm288.03 4.63c-.8 17.03-5.03 30.47-12.57 40.31-7.57 9.85-17.83 14.77-30.78 14.77-12.36 0-20.6-5.24-24.75-15.74-3.49 5.16-7.54 9.07-12.11 11.65-4.61 2.59-9.43 3.88-14.49 3.88-9.95 0-17.49-4.08-22.66-12.25-5.13-8.17-7.09-19.1-5.86-32.78 1.08-11.1 3.8-21.12 8.13-30.02 4.33-8.94 9.81-15.81 16.44-20.7 6.67-4.85 13.72-7.3 21.22-7.3 5.73 0 10.79.7 15.19 2.13s9.57 4.4 15.5 8.9l-5.31 57.5c-1.29 13.47 2.59 20.21 11.66 20.21 6.95 0 12.67-3.7 17.14-11.17 4.44-7.47 6.88-17.11 7.3-28.98 1.15-25.1-3.7-44.33-14.56-57.7-10.89-13.33-27.23-20-49.04-20-13.37 0-25.21 3.35-35.54 10.02-10.33 6.67-18.54 16.33-24.61 28.97s-9.39 27.02-10.02 43.18c-.84 16.41 1.15 30.58 5.87 42.45 4.74 11.9 12.01 20.95 21.78 27.16 9.81 6.17 21.75 9.28 35.85 9.28 5.73 0 11.73-.7 17.94-2.06 6.25-1.36 11.56-3.17 15.92-5.51l3.87 14c-4.15 2.72-9.74 4.92-16.82 6.56-7.05 1.67-14.14 2.51-21.29 2.51-17.35 0-32.19-3.67-44.62-11-12.39-7.33-21.71-17.94-27.92-31.83-6.39-14.38-9.22-31.59-8.48-51.63.83-18.64 5.02-35.43 12.6-50.33 7.54-14.88 17.91-26.46 31.03-34.7 13.12-8.24 28.06-12.36 44.82-12.36 17 0 31.59 3.74 43.85 11.21 12.21 7.43 21.39 18.18 27.43 32.18 6.08 14 8.7 30.41 7.89 49.19zm-103.18 9.87c-.88 9.26-.07 16.27 2.44 21.05 2.55 4.79 6.56 7.19 12.08 7.19 3.66 0 7.15-1.6 10.43-4.85 3.28-3.21 5.94-7.64 7.96-13.3l4.61-50.3c-3.42-1.29-6.7-1.92-9.91-1.92-7.58 0-13.76 3.56-18.5 10.65-4.78 7.12-7.82 17.59-9.11 31.48zM335.29 31.42v65.61h62.96l-62.96-65.61zm71.17 84.23h-80.48c-5.14 0-9.31-4.17-9.31-9.31V18.62H56.44v199.99l173.68 155.15 176.34-154.05V115.65zm39.75 373.71-160.9-139.19-49.15 42.94c-3.47 3.04-8.76 3.08-12.28-.07l-47.82-42.72L18.62 486.01v5.35c0 .63.26 1.21.68 1.62.41.42.99.68 1.61.68h423.01a2.301 2.301 0 0 0 2.29-2.3v-2zM299.42 337.85l146.79 126.98V210.91c0-.35-.07-.73-.19-1.13l-146.6 128.07zM18.62 461.52l143.49-123.66-143.3-128.02c-.13.38-.19.74-.19 1.07v250.61z"/>
                    </svg>
                    <label> - baillet.nathan@gmail.com</label>
                </div>
                <div class="pb-4">
                    <svg class="h-10 w-10 text-green-500 fill-current inline" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 122.88 122.267" enable-background="new 0 0 122.88 122.267" xml:space="preserve">
                        <path d="M33.822,50.291c4.137,7.442,8.898,14.604,15.074,21.133C55.1,77.984,62.782,83.962,72.771,89.03l0.01,0.005l0.002-0.005 c0.728,0.371,1.421,0.362,2.072,0.118c0.944-0.353,1.927-1.137,2.883-2.086c0.729-0.726,1.643-1.924,2.631-3.223 c3.846-5.054,8.601-11.301,15.314-8.193c0.142,0.065,0.276,0.141,0.402,0.226l22.373,12.852c0.08,0.046,0.157,0.095,0.23,0.147 c2.966,2.036,4.177,5.172,4.19,8.683c0.014,3.621-1.329,7.674-3.274,11.101c-2.565,4.517-6.387,7.502-10.761,9.525 c-4.17,1.928-8.798,2.954-13.267,3.608c-6.989,1.025-13.578,0.374-20.288-1.692c-6.55-2.017-13.176-5.385-20.4-9.86l-0.526-0.326 c-3.326-2.06-6.906-4.276-10.389-6.904C31.108,93.296,18.007,79.283,9.512,63.904C2.361,50.958-1.552,36.995,0.581,23.681 C1.75,16.375,4.901,9.743,10.333,5.35c4.762-3.853,11.188-5.94,19.448-5.203c0.973,0.084,1.793,0.639,2.255,1.419l0.006-0.003 l14.324,24.27c2.11,2.718,2.344,5.415,1.203,8.096c-0.943,2.218-2.892,4.251-5.476,6.168c-0.786,0.65-1.708,1.325-2.659,2.021 C36.236,44.459,32.578,47.136,33.822,50.291L33.822,50.291z M44.67,75.422C38.066,68.44,33.035,60.88,28.695,53.065 c-0.076-0.123-0.144-0.253-0.202-0.39c-3.174-7.459,2.52-11.625,7.493-15.262c0.845-0.618,1.663-1.217,2.401-1.829l0.002,0.003 c0.043-0.036,0.088-0.071,0.135-0.105c1.843-1.354,3.171-2.647,3.678-3.837c0.289-0.679,0.182-1.426-0.466-2.265 c-0.111-0.129-0.213-0.271-0.303-0.423L27.795,5.852c-5.869-0.241-10.419,1.321-13.784,4.044 c-4.239,3.429-6.723,8.759-7.674,14.699c-1.905,11.894,1.716,24.594,8.292,36.5c8.078,14.623,20.575,27.977,32.864,37.25 c3.379,2.55,6.776,4.653,9.932,6.607l0.526,0.326c6.818,4.223,13.017,7.386,19.052,9.244c5.876,1.809,11.634,2.38,17.729,1.486 c4.009-0.587,8.113-1.485,11.668-3.129c3.351-1.55,6.248-3.785,8.134-7.104c1.496-2.637,2.53-5.653,2.521-8.222 c-0.006-1.63-0.472-3.029-1.605-3.844L93.2,80.93c-2.461-1.081-5.629,3.081-8.193,6.45c-1.104,1.452-2.125,2.792-3.156,3.817 c-1.477,1.466-3.118,2.723-4.962,3.411c-2.136,0.799-4.395,0.834-6.755-0.37l0.002-0.004C59.522,88.849,51.323,82.457,44.67,75.422 L44.67,75.422z"/>
                    </svg>
                    <label> - 07544722713</label>
                </div>
                <div>
                    <svg class="h-10 w-10 text-green-500 fill-current  inline" xmlns="http://www.w3.org/2000/svg" shape-rendering="geometricPrecision" text-rendering="geometricPrecision" image-rendering="optimizeQuality" fill-rule="evenodd" clip-rule="evenodd" viewBox="0 0 512 509.64">
                        <rect width="512" height="509.64" rx="115.61" ry="115.61"/>
                        <path class="text-stone-800" d="M204.97 197.54h64.69v33.16h.94c9.01-16.16 31.04-33.16 63.89-33.16 68.31 0 80.94 42.51 80.94 97.81v116.92h-67.46l-.01-104.13c0-23.81-.49-54.45-35.08-54.45-35.12 0-40.51 25.91-40.51 52.72v105.86h-67.4V197.54zm-38.23-65.09c0 19.36-15.72 35.08-35.08 35.08-19.37 0-35.09-15.72-35.09-35.08 0-19.37 15.72-35.08 35.09-35.08 19.36 0 35.08 15.71 35.08 35.08zm-70.17 65.09h70.17v214.73H96.57V197.54z"/>
                    </svg>
                    <a href="https://www.linkedin.com/in/nathan-baillet/"> - https://www.linkedin.com/in/nathan-baillet/</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const sections = ['About', 'Projects', 'Contact'];
let activeSection = ref(sections[0]);

function setActiveSection(section) {
    activeSection.value = section;
}

function getActiveClass(section) {
    if (activeSection.value === section) return "text-green-400";
    return "";
}

</script>
