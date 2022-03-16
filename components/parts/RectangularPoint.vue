<template>
  <div
    :class='`${isSelected? "rectangular-selected": "rectangular-notSelected"} rectangular-${mode}`'
    class='rectangular '></div>
</template>

<script>
export default {
  name: 'RectangularPoint',
  props: {
    isSelected: {
      type: Boolean,
      default: true
    },
    mode: {
      type: String,
      default: 'mypage'
    }
  }
}
</script>

<style lang='scss' scoped>
.rectangular {
  position: relative;
}

.rectangular-mypage {
  width: 4px;
  height: 4px;
  margin-left: 0.4vw;
  margin-top: 1vh;
}

.rectangular-bookmark {
  width: 8px;
  height: 8px;
  margin-left: 0.4vw;
  margin-top: 1vh;
}

.rectangular-selected {
  background: $dark-191919 !important;
}

.rectangular-notSelected {
  background: $grey-3;
}
</style>
