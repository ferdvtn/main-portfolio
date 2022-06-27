<template>
  <div class="min-h-screen">
    <Nuxt />
    <footer
      class="bg-gray-200 text-gray-800 dark:bg-gray-900 dark:text-gray-300 mt-40 md:mt-60 py-3 md:py-6 px-3 text-xs text-center"
    >
      <p class="leading-loose">Copyright &copy; {{ currentYear }}, Ahmad Ferdian<br>All Rights Reserved</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    }
  }
}
</script>