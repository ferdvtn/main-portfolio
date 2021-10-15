<template>
  <div class="relative min-h-screen">
      <img src="~/assets/img/user.png" alt="user" class="w-64 h-auto bg-gradient-to-r from-purple-600 to-blue-600 shadow-xl rounded-full absolute left-0 top-1/4 transform -translate-x-1/3">
      <div class="absolute top-1/3 right-3">
        <h1 class="text-4xl font-bold antialiased">Ahmad Ferdian</h1>
        <p data-aos="fade-right">Web Developer</p>

        <div class="mt-5 flex space-x-2 justify-start text-center">
          <a href="/pdf/ahmad-ferdian-cv.pdf" target="_blank" class="py-2 px-4 bg-red-300 text-gray-700 font-semibold antialiased rounded">Download CV</a>
          <NuxtLink to="/aboutme" class="flex-1 py-2 px-4 bg-green-300 text-gray-700 font-semibold antialiased rounded">About me</NuxtLink>
        </div>
      </div>
  </div>
</template>

<script>
export default {}
</script>