<template>
  <div :class='showOthers' :style='styleObject'>
    <div v-if='showOthers' class='thumbnail-box'>
      <div class='thumbnail-title'>DATABASE</div>
      <div class='mini-box'></div>
      <div class='main-box'></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ThumNail',
  props: {
    styleObject: {
      type: Object,
      default: () => ({
        width: '138px',
        height: '138px',
        background: '#F2F2F2'
      })
    },
    showOthers: {
      type: Boolean,
      default: true
    }
  }
}
</script>

<style lang='scss' scoped>
.thumbnail-box {
  position: relative;
  width: 100%;
  height: 100%;
}

.thumbnail-title {
  font-family: "Chakra Petch";
  font-weight: 600;
  font-size: 1.625rem;
  text-transform: uppercase;
  color: $dark-191919;
  font-weight: 600;
  width: 66px;
  word-wrap: break-word;
  line-height: 26px;
  position: absolute;
  top: 25px;
  left: 15px;
}

.mini-box {
  width: 6px;
  height: 6px;
  background-color: $grey-3;
  position: absolute;
  top: 4px;
  right: 4px;
}

.main-box {
  position: absolute;
  width: 14px;
  height: 64px;
  background-color: $blue;
  bottom: 0;
  right: 0;

}
</style>
