<template>
  <div class="relative min-h-screen flex flex-col justify-center p-5">
    <h1 class="font-semibold antialiased text-xl">Experiences</h1>
    <DividerX h="1" w="10" class="mt-3 mb-8" />

    <ul class="jobs">
      <li class="job" v-for="expr in experiences" :key="expr.id">
        <div class="dot"></div>
        <h2 class="font-semibold antialiased">{{ expr.title }}</h2>
        <p class="text-sm">{{ expr.company }}</p>
        <small>{{ expr.date }}</small>
      </li>
    </ul>

    <TurnBack target='/aboutme' />
  </div>
</template>

<script>
import { experiences } from '~/assets/data.js';

export default {
  data() {
    return {
      experiences: experiences
    }
  }
}
</script>

<style scoped>
  .jobs {
    @apply pl-4 border-l-2 border-purple-600 flex flex-col items-start space-y-4
  }

  .job {
    @apply py-3 px-5 relative bg-gradient-to-r from-purple-500 to-blue-500 inline-block rounded-lg
  }

  .dot {
    @apply w-4 h-4 bg-purple-600 rounded-full absolute -left-6 top-10
  }
</style>