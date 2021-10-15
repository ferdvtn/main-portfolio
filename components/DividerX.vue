<template>
  <div :class="[`w-${w}`, `h-${h}`]" class="bg-gradient-to-r from-purple-600 to-blue-600 rounded-full"></div>
</template>

<script>
export default {
  props: ['w', 'h']
}
</script>