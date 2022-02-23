<template>
  <svg :width="width" :height="height" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M3 4.7998H21V5.9998H3V4.7998Z" fill="#191919"/>
    <path d="M3 11.3998H21V12.5998H3V11.3998Z" fill="#191919"/>
    <path d="M3 17.9998H21V19.1998H3V17.9998Z" fill="#191919"/>
  </svg>

</template>

<script>
  export default {
    props: {
      width: {
        type: [Number, String],
        default: 24
      },
      height: {
        type: [Number, String],
        default: 24
      },
    }
  }
</script>


