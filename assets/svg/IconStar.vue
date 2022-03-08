<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 41 40' xmlns='http://www.w3.org/2000/svg'>
    <path
      d='M15.5562 15.5L20.0728 3.5L24.5895 15.5L36.6339 20L24.5895 24.5L20.0728 36.5L15.5562 24.5L3.51172 20L15.5562 15.5Z'
      fill='#191919' stroke='#191919' />
    <rect fill='#6CF080' height='4' width='4.01482' x='18.0664' y='18' />
  </svg>
</template>

<script>
export default {
  props: {
    width: {
      type: [Number, String],
      default: 41
    },
    height: {
      type: [Number, String],
      default: 40
    }
  }
}
</script>


