<template>
  <button @click="scrollToTop" class="fixed bottom-5 right-5" :class="{'invisible': (scrollPosition < 230)}">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" /> </svg>
  </button>
</template>

<script>
export default {
  data() {
    return {
      scrollPosition: null
    }
  },
  methods: {
    scrollToTop() {
      window.scrollTo({top: 0, behavior: 'smooth'});
    },
    updateScroll() {
      this.scrollPosition = window.scrollY;
    }
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }
}
</script>