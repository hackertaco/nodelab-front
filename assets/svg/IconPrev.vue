<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 19 32' xmlns='http://www.w3.org/2000/svg'>
    <path
      clip-rule='evenodd'
      d='M18.7466 2.1858L3.86962 16.0001L18.7466 29.8145L17.3857 31.28L0.930389 16.0001L17.3857 0.720215L18.7466 2.1858Z'
      fill='#191919'
      fill-rule='evenodd' />
  </svg>
</template>

<script>
export default {
  name: 'IconPrev',
  props: {
    width: {
      type: [Number, String],
      default: 19
    },
    height: {
      type: [Number, String],
      default: 32
    }
  }
}
</script>

<style scoped>

</style>
