<template>
  <svg
    v-if='bookmarkSelected' :height='height' :width='width' fill='none' viewBox='0 0 24 24'
    xmlns='http://www.w3.org/2000/svg'>
    <path d='M4 2H20V22L12 17.5L4 22V2Z' fill='#191919' />
    <rect fill='#6CF080' height='4' width='4' x='10' y='8' />
  </svg>
  <svg v-else fill='none' height='20' viewBox='0 0 16 20' width='16' xmlns='http://www.w3.org/2000/svg'>
    <path
      d='M7.50974 14.6284L1 18.2902V1H15V18.2902L8.49026 14.6284L8 14.3527L7.50974 14.6284Z' stroke='#C4C4C4'
      stroke-width='2' />
  </svg>

</template>

<script>
export default {
  name: 'IconBookmark',
  props: {
    bookmarkSelected: {
      type: Boolean,
      default: true
    },
    width: {
      type: [Number, String],
      default: 19
    },
    height: {
      type: [Number, String],
      default: 19
    }
  }
}
</script>

<style scoped>

</style>
