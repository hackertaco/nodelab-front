<template>
  <svg
    v-if='chatSelected' :height='height' :width='width' fill='none' viewBox='0 0 24 24'
    xmlns='http://www.w3.org/2000/svg'>
    <path d='M4 4H20V17H13.5L12 19.5L10.5 17H4V4Z' fill='#191919' />
    <path
      d='M2.5 2.25H2.25V2.5V17.7857V18.0357H2.5H9.82947L11.7724 22.3122L12 22.8132L12.2276 22.3122L14.1705 18.0357H21.5H21.75V17.7857V2.5V2.25H21.5H2.5ZM10.8621 16.6823L10.7955 16.5357H10.6345H3.75V3.75H20.25V16.5357H13.3655H13.2045L13.1379 16.6823L12 19.1868L10.8621 16.6823Z'
      fill='#191919' stroke='#191919' stroke-width='0.5' />
    <path d='M6.3999 9H8.7999V11.4H6.3999V9Z' fill='#6CF080' />
    <path d='M10.7998 9H13.1998V11.4H10.7998V9Z' fill='#6CF080' />
    <path d='M15.2002 9H17.6002V11.4H15.2002V9Z' fill='#6CF080' />
  </svg>
  <svg v-else :height='height' :width='width' fill='none' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg'>
    <path
      d='M2.5 2.25H2.25V2.5V17.7857V18.0357H2.5H9.82947L11.7724 22.3122L12 22.8132L12.2276 22.3122L14.1705 18.0357H21.5H21.75V17.7857V2.5V2.25H21.5H2.5ZM10.8621 16.6823L10.7955 16.5357H10.6345H3.75V3.75H20.25V16.5357H13.3655H13.2045L13.1379 16.6823L12 19.1868L10.8621 16.6823Z'
      fill='#191919' stroke='#191919' stroke-width='0.5' />
    <path d='M6.3999 9H8.7999V11.4H6.3999V9Z' fill='#191919' />
    <path d='M10.7998 9H13.1998V11.4H10.7998V9Z' fill='#191919' />
    <path d='M15.2002 9H17.6002V11.4H15.2002V9Z' fill='#191919' />
  </svg>
</template>

<script>
export default {
  name: 'IconComment',
  props: {
    chatSelected: {
      type: Boolean,
      default: false
    },
    width: {
      type: [Number, String],
      default: 17
    },
    height: {
      type: [Number, String],
      default: 18
    }
  }
}
</script>

<style scoped>

</style>
