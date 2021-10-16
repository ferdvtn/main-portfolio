<template>
  <div class="theme-switch-wrapper flex justify-center items-center absolute right-5 top-5">
    <em :class="['icon-dark', 'mr-5 md:mr-0 md:ml-5', {'hidden': !darkTheme}]"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" /> </svg></em>
    <em :class="['icon-light', 'mr-5 md:mr-0 md:ml-5', {'hidden': darkTheme}]"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"> <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" /> </svg></em>
    
    <label class="order-last md:order-first theme-switch" for="checkbox">
      <input @change="switchTheme($event)" type="checkbox" id="checkbox" checked />
      <div class="slider round"></div>
    </label>
  </div>
</template>

<script>
export default {
  data() {
    return {
      darkTheme: true
    }
  },
  methods: {
    switchTheme(e) {
      const html = document.querySelector('html');
      this.darkTheme = e.target.checked;
      if (this.darkTheme) {
        html.classList.add('dark');
      } else
        html.classList.remove('dark');
    }
  }
}
</script>

<style scoped>
  .theme-switch-wrapper {
    display: flex;
    align-items: center;
  }

  .theme-switch-wrapper em {
    font-size: 1rem;
  }

  .theme-switch {
    display: inline-block;
    height: 34px;
    position: relative;
    width: 60px;
  }

  .theme-switch input {
    display:none;
  }

  .slider {
    background-color: #ccc;
    bottom: 0;
    cursor: pointer;
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
    transition: .4s;
  }

  .slider:before {
    background-color: #fff;
    bottom: 4px;
    content: "";
    height: 26px;
    left: 4px;
    position: absolute;
    transition: .4s;
    width: 26px;
  }

  input:checked + .slider {
    background-color: #66bb6a;
  }

  input:checked + .slider:before {
    transform: translateX(26px);
  }

  .slider.round {
    border-radius: 34px;
  }

  .slider.round:before {
    border-radius: 50%;
  }
</style>