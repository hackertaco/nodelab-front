<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 22 22' xmlns='http://www.w3.org/2000/svg'>
    <path
clip-rule='evenodd' d='M9.93881 11L0.869141 1.93029L1.9298 0.869629L10.9995 9.9393L20.0691 0.869629L21.1298 1.93029L12.0601 11L21.1298 20.0696L20.0691 21.1303L10.9995 12.0606L1.9298 21.1303L0.869141 20.0696L9.93881 11Z'
          fill='#191919'
          fill-rule='evenodd' />
  </svg>
</template>

<script>
export default {
  props: {
    width: {
      type: [Number, String],
      default: 22
    },
    height: {
      type: [Number, String],
      default: 22
    }
  }
}
</script>


