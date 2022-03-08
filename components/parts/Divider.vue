<template>
  <div class='divider-container'>
    <div :class='`${color}-line`'></div>
    <div :class='`${color}-rect`'></div>
    <div class='main-rect'></div>
  </div>
</template>

<script>
export default {
  name: 'DividerLine',
  props: {
    color: {
      type: String,
      default: 'main'
    }
  }

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

.grey-line {
  width: 100%;
  border: 2px solid $grey-3;
}

.main-rect {
  width: 100%;
  background-color: #F7f7f7;
  height: 2vh;
}

.grey-rect {
  background: $grey-3;
  width: 8%;
  height: 1vh;
  position: absolute;
  right: 0;
  z-index: 10;
}

.right-rect {
  background: #191919;
  width: 8%;
  height: 1vh;
  position: absolute;
  right: 0;
  z-index: 10;
}
</style>
