<template>
  <svg
    v-if='likeSelected' :height='height' :width='width' fill='none' viewBox='0 0 24 24'
    xmlns='http://www.w3.org/2000/svg'>
    <path d='M2 13L12 22L22 13V7L18.5 3H15L12 5.5L9 3H5.5L2 7V13Z' fill='#191919' />
    <path
      clip-rule='evenodd'
      d='M12 5.5L9 3H5.5L2 7V13L12 22L22 13V7L18.5 3H15L12 5.5ZM16.4482 7L12 10.7068L7.55181 7H7.31507L6 8.50294V11.2185L12 16.6186L18 11.2186V8.50294L16.6849 7H16.4482Z'
      fill='#191919'
      fill-rule='evenodd' />
    <path d='M10 9.5H14V13.5H10V9.5Z' fill='#6CF080' />
  </svg>
  <svg v-else fill='none' height='19' viewBox='0 0 22 21' width='20' xmlns='http://www.w3.org/2000/svg'>
    <path
      d='M8.16005 0.807944L8.09051 0.75H8H4.5H4.38656L4.31186 0.835374L0.811856 4.83537L0.75 4.90607V5V11V11.1113L0.832759 11.1858L10.8328 20.1858L11 20.3363L11.1673 20.1858L21.1672 11.1858L21.25 11.1113V11V5V4.90607L21.1881 4.83537L17.6881 0.835374L17.6134 0.75H17.5H14H13.9095L13.84 0.807945L11 3.17457L8.16005 0.807944ZM10.84 4.99376L11 5.12714L11.1601 4.99376L14.4526 2.25H16.9328L19.75 5.46967V10.4433L11 18.3183L2.25 10.4433V5.46967L5.06721 2.25H7.54744L10.84 4.99376Z'
      fill='#191919' stroke='#191919' stroke-width='0.5' />
  </svg>

</template>

<script>
export default {
  name: 'IconLike',
  props: {
    likeSelected: {
      type: Boolean,
      default: true
    },
    width: {
      type: [Number, String],
      default: 19
    },
    height: {
      type: [Number, String],
      default: 20
    }
  }
}
</script>

<style scoped>

</style>
