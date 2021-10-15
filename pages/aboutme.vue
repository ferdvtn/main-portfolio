<template>
  <div class="relative text-center min-h-screen flex flex-col justify-center items-center p-5">
    <h1 class="font-semibold antialiased text-xl">About Me</h1>
    <DividerX w='10' h='1' class="mt-3 mb-8" />

    <p class="mb-16 text-sm leading-relaxed">Ahmad Ferdian, my last job as an IT web developer at PT Tira Satria Niaga in Jakarta area. Information systems graduate student in 2020 with GPA of 3.6 of 4.0. In my self, Honesty is the principle during work</p>

    <div class="flex justify-center items-center space-x-2">
      <NuxtLink to="/experiences" class="py-2 px-4 rounded bg-gradient-to-r from-pink-600 to-indigo-600">Experience</NuxtLink>
      <a href="https://www.linkedin.com/in/ahmadferdian/" target="_blank" class="py-2 px-4 rounded bg-blue-900 tracking-wider">Linkedin</a>
    </div>
    <NuxtLink to="/experiences" class="mt-2 py-2 px-4 rounded bg-gradient-to-r from-purple-600 via-pink-600 to-red-500">Let's Connected</NuxtLink>

    <TurnBack />
  </div>
</template>