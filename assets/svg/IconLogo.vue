<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 18 16' xmlns='http://www.w3.org/2000/svg'>
    <path :fill='color' d='M15.3673 14.1778L3.39796 0.200195H0V1.8226H2.63265L14.602 15.8002H18V14.1778H15.3673Z' />
    <path :fill='color' d='M2.60204 14.1777H0V15.8001H2.60204V14.1777Z' />
    <path :fill='color' d='M17.9998 0.200195H15.3672V1.8538H17.9998V0.200195Z' />
  </svg>

</template>

<script>
export default {
  name: 'IconLogo',
  props: {
    color: {
      type: String,
      default: '#ffffff'
    },
    width: {
      type: [Number, String],
      default: 18
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
