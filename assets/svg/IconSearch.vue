<template>
  <svg
    :width="width"
    :height="height"
    viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path fill-rule="evenodd" clip-rule="evenodd" d="M11.3499 14.4377H6.98341L3.89583 11.3501V6.98278L6.98328 3.896H11.35L14.4375 6.98278V11.3501L11.3499 14.4377ZM16.5 12.2044L12.2042 16.5002H6.1291L1.83333 12.2044V6.12834L6.1291 1.8335H12.2042L16.5 6.12834V12.2044Z" fill="#191919"/>
    <path fill-rule="evenodd" clip-rule="evenodd" d="M18.521 19.9794L13.021 14.4794L14.4794 13.021L19.9794 18.521L18.521 19.9794Z" fill="#191919"/>
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
      },
    }
  }
</script>


