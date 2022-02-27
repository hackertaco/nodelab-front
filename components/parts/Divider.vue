<template>
  <div class='divider-container'>
    <div class='main-line'></div>
    <div class='right-rect'></div>
    <div class='main-rect'></div>
  </div>
</template>

<script>
export default {
  name: 'DividerLine'
}
</script>

<style lang='scss' scoped>
.divider-container {
  width: 100%;
  position: relative;
}

.main-line {
  width: 100%;
  border: 2px solid #191919;
}

.main-rect {
  width: 100%;
  background-color: #F7f7f7;
  height: 30px;
}

.right-rect {
  background: #191919;
  width: 8%;
  height: 12px;
  position: absolute;
  right: 0;
  z-index: 10;
}
</style>
