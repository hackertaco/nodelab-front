<template>
  <div class='title-container'>
    <slot name='title'>타이틀</slot>
  </div>
</template>

<script>
export default {
  name: 'ProfileTitle'
}
</script>

<style lang='scss' scoped>
.title-container {
  font-size: $eng-24;
  font-weight: 600;
}
</style>
