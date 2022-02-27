<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 54 81' xmlns='http://www.w3.org/2000/svg'>
    <path
clip-rule='evenodd' d='M30.3011 0V68.8335L49.4767 49.6518L53.7922 53.9672L27.2535 80.4998L0.714844 53.9672L5.03027 49.6518L24.2059 68.8335V0H30.3011Z'
          fill='#191919'
          fill-rule='evenodd' />
  </svg>
</template>

<script>
export default {
  name: 'IconDown',
  props: {
    width: {
      type: [Number, String],
      default: 54
    },
    height: {
      type: [Number, String],
      default: 81
    }
  }
}
</script>

<style scoped>

</style>
