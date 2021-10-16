<template>
  <div class="relative md:container mx-auto py-10 flex flex-col space-y-32">
      <Switcher />

      <div id="hero" class="relative p-4 flex justify-center items-center h-64 md:space-x-8">
        <img src="~/assets/img/user.png" alt="user" class="w-64 h-auto bg-gradient-to-r from-purple-600 to-blue-600 shadow-xl rounded-full absolute -left-24 md:relative md:left-0">
        <div class="z-10 absolute right-3 md:relative md:right-0">
          <h1 class="text-4xl font-bold antialiased">Ahmad Ferdian</h1>
          <p data-aos="fade-right">Web Developer</p>

          <div class="mt-5 flex space-x-2 justify-start text-center">
            <a href="/pdf/ahmad-ferdian-cv.pdf" target="_blank" class="py-2 px-4 bg-red-300 text-gray-700 font-semibold antialiased rounded">Download CV</a>
            <button @click="scrollToId('experiences')" class="py-2 px-4 bg-green-300 text-gray-700 font-semibold antialiased rounded">Experiences</button>
          </div>
        </div>
      </div>

      <!-- aboutme -->
      <div id="aboutme" class="p-4 flex flex-col justify-start items-center">
        <h1 class="font-semibold antialiased text-xl">About me</h1>
        <DividerX class="mt-3 mb-8" />

        <p class="mb-16 text-sm text-center leading-relaxed max-w-md">Hello, I'm Ferdian. My current job as an IT web developer at <i><strong>Tira Satria Niaga</strong></i> company in Jakarta area. Information systems graduate student in 2020 with GPA of 3.6 of 4.0.<br>In my self, Honesty is the principle during work</p>

        <div class="flex justify-center items-center space-x-2 text-gray-100">
          <button @click="scrollToId('educations')" class="py-2 px-4 rounded bg-gradient-to-r from-pink-600 to-indigo-600">Educations</button>
          <a href="https://www.linkedin.com/in/ahmadferdian/" target="_blank" class="py-2 px-4 rounded bg-blue-900 tracking-wider">Linkedin</a>
        </div>
        <button @click="scrollToId('contact')" class="mt-2 py-2 px-4 text-gray-100 rounded bg-gradient-to-r from-purple-600 to-pink-600">Let's Connected</button>
      </div>

      <!-- experiences & educations -->
      <div class="flex flex-col space-y-32 p-4 md:space-y-0 justify-evenly items-start md:flex-row">
        <div id="experiences" class="w-full flex flex-col justify-start items-start md:items-center">
          <div class="w-full flex flex-col items-center">
            <h1 class="font-semibold antialiased text-xl text-center">Experiences</h1>
            <DividerX class="mt-3 mb-8" />
          </div>
          <ul class="pl-4 border-l-2 border-purple-600 flex flex-col items-start space-y-5">
            <li v-for="expr in experiences" :key="expr.id" class="py-3 px-6 relative text-gray-100 bg-gradient-to-r from-purple-600 to-blue-500 inline-block rounded-lg">
              <div class="w-4 h-4 bg-purple-600 rounded-full absolute -left-6 top-10"></div>
              <h2 class="font-semibold antialiased">{{ expr.title }}</h2>
              <p class="text-sm">{{ expr.company }}</p>
              <small>{{ expr.date }}</small>
            </li>
          </ul>
        </div>
        <div id="educations" class="w-full flex flex-col justify-start items-start md:items-center">
          <div class="w-full flex flex-col items-center">
            <h1 class="font-semibold antialiased text-xl text-center">Educations</h1>
            <DividerX class="mt-3 mb-8" />
          </div>
          <ul class="pl-4 border-l-2 border-purple-600 flex flex-col items-start space-y-5">
            <li v-for="educ in educations" :key="educ.id" class="py-3 px-6 relative text-gray-100 bg-gradient-to-r from-purple-600 to-blue-500 inline-block rounded-lg">
              <div class="w-4 h-4 bg-purple-600 rounded-full absolute -left-6 top-10"></div>
              <h2 class="font-semibold antialiased">{{ educ.name }}</h2>
              <p class="text-sm">{{ educ.major }}</p>
              <small>{{ educ.date }}</small>
            </li>
          </ul>
        </div>
      </div>

      <!-- Tools -->
      <div id="tools" class="flex flex-col justify-center items-center px-5 py-10 bg-gradient-to-t md:bg-gradient-to-r from-pink-600 via-purple-600 to-blue-600 md:rounded-xl">
        <h1 class="text-gray-100 font-semibold antialiased text-lg">Tools</h1>
        <DividerX class="mt-3 mb-5" />
        <ul class="w-full flex flex-wrap justify-center items-center">
          <li v-for="i in tools" :key="i.id" class="m-5">
            <a :href="`${i.url}`" target="_blank" class="rounded block transform hover:scale-110 focus:outline-none focus:ring-2 focus:ring-pink-400 focus:ring-offset-2 focus:ring-offset-blue-300 transition duration-100">
              <img 
                :src="require(`~/assets/img/tools/${i.id}.png`)" :alt="`${i.id}.png`"
                class="w-16 h-auto md:w-32"
              >
            </a>
          </li>
        </ul>
      </div>

      <!-- projects -->
      <div id="projects" class="flex flex-col justify-start items-center md:items-start">
        <h1 class="font-semibold antialiased text-lg">Personal projects</h1>
        <DividerX class="mt-3 mb-8" />
        <ul class="flex flex-col justify-start items-center w-full md:-m-3 space-y-5 md:flex-wrap md:flex-row md:space-y-0">
          <li v-for="project in projects" :key="project.id" class="w-full md:w-1/3">
            <div class="md:m-3 bg-gradient-to-r from-pink-600 to-purple-600 md:rounded-xl">
              <img 
                :src="require(`~/assets/img/projects/${project.id}.png`)" :alt="`${project.id}.png`"
                class="w-full h-56 object-contain object-center"
              >
            </div>
          </li>
        </ul>
      </div>

      <!-- contact -->
      <div id="contact" class="px-5">
        <h1 class="font-semibold antialiased text-lg">Let's connected</h1>
        <DividerX class="mt-3 mb-8" />
        <ul class="flex flex-col space-y-2">
          <li class="flex items-center space-x-3">
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207" /> </svg>
            </div>
            <p>hayferdian@gmail.com</p>
          </li>
          <li class="flex items-center space-x-3">
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" /> </svg>
            </div>
            <p>+62 878-8991-4778</p>
          <li class="flex items-center space-x-3">
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" /> </svg>
            </div>
            <a href="https://ahmadferdian.netlify.app" target="_blank">ahmadferdian.netlify.app</a>
          </li>
        </ul>
      </div>

      <ArrowTop />
  </div>
</template>

<script>
import { experiences, educations, tools, projects } from '~/assets/data.js';

export default {
  data() {
    return {
      experiences: experiences,
      educations: educations,
      tools: tools,
      projects: projects
    }
  },
  methods: {
    scrollToId(id) {
      const target = document.querySelector(`#${id}`);
      window.scroll({
        behavior: 'smooth',
        left: 0,
        top: target.offsetTop
      });
    }
  }
}
</script>