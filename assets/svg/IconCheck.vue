<template>
  <svg
    v-if='settingSelected' :height='height' :width='width' fill='none' viewBox='0 0 32 32'
    xmlns='http://www.w3.org/2000/svg'>
    <rect fill='#191919' height='32' width='32' />
    <rect fill='#6CF080' height='16' width='16' x='8' y='8' />
  </svg>
  <svg v-else :height='height' :width='width' fill='none' viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'>
    <rect fill='#E5E5E5' height='32' width='32' />
  </svg>

</template>

<script>
export default {
  name: 'IconCheck',
  props: {
    settingSelected: {
      type: Boolean,
      default: false
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
