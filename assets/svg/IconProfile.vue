<template>
  <svg :height='height' :width='width' fill='none' viewBox='0 0 132 132' xmlns='http://www.w3.org/2000/svg'>
    <path
      d='M13.7998 59.299L36.1712 23.5879H65.9998H95.8284L118.2 59.299L65.9998 111.675L13.7998 59.299Z'
      fill='#47EADE' />
    <path
      clip-rule='evenodd'
      d='M13.7998 59.299L65.9998 111.675L118.2 59.299L95.8284 23.5879H36.1712L13.7998 59.299ZM38.7273 65.824L65.9998 93.1887L93.2723 65.824H38.7273ZM98.7129 52.774H79.9517L90.6724 39.9391L98.7129 52.774ZM76.4263 36.6379H55.5733L65.9998 49.1206L76.4263 36.6379ZM52.0479 52.774L41.3272 39.9391L33.2867 52.774H52.0479Z'
      fill='#191919'
      fill-rule='evenodd' />
  </svg>


</template>

<script>
export default {
  name: 'IconProfile',
  props: {
    width: {
      type: [Number, String],
      default: '6.8vw'
    },
    height: {
      type: [Number, String],
      default: '12.2vh'
    }
  }
}
</script>

<style scoped>

</style>
