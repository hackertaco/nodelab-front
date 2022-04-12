<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 174 174' xmlns='http://www.w3.org/2000/svg'>
    <path
      d='M38.0625 89.7188L87.0001 133.219L135.938 89.7188V67.9688L111.469 43.5H100.05L87.0001 54.375L73.95 43.5H59.8125L38.0625 67.9688V89.7188Z'
      fill='#FF5531' />
    <path
      clip-rule='evenodd'
      d='M87.0001 54.375L73.95 43.5H59.8125L38.0625 67.9688V89.7188L87.0001 133.219L135.938 89.7188V67.9688L111.469 43.5H100.05L87.0001 54.375ZM105.111 64.056L87.0001 79.1481L67.806 63.1531L57.0938 75.2044V81.1725L87.0001 107.756L116.906 81.1725V75.8517L105.111 64.056Z'
      fill='#191919'
      fill-rule='evenodd' />
  </svg>

</template>

<script>
export default {
  name: 'IconProfileHeart',
  pros: {
    width: {
      type: [Number, String],
      default: 22
    },
    height: {
      type: [Number, String],
      default: 22
    }
  },
  setup() {

  }
}
</script>

<style scoped>

</style>
