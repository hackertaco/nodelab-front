<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 10 16' xmlns='http://www.w3.org/2000/svg'>
    <path
      clip-rule='evenodd'
      d='M0.464844 14.9078L7.90333 8.00067L0.464844 1.09351L1.1453 0.360714L9.37294 8.00067L1.14529 15.6406L0.464844 14.9078Z'
      fill='#191919'
      fill-rule='evenodd' />
  </svg>
</template>

<script>
export default {
  name: 'IconNext',
  props: {
    width: {
      type: [Number, String],
      default: 10
    },
    height: {
      type: [Number, String],
      default: 16
    }
  }
}
</script>

<style scoped>

</style>
