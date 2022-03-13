<template>
  <div class='btn-container'>
    <slot name='btnName'>버튼명</slot>
    <div class='rectangular'></div>
  </div>
</template>

<script>
export default {
  name: 'ButtonContainer'
}
</script>

<style lang='scss' scoped>
.btn-container {
  width: 100%;
  height: 5.9vh;
  background: $mint;
  display: flex;
  position: relative;
  justify-content: center;
  align-items: center;
  font-weight: 700;
  font-size: $kor-20;
  cursor: pointer;
}


.rectangular {
  width: 8px;
  height: 8px;
  background: $dark-191919;
  position: absolute;
  top: 8px;
  right: 8px;
}
</style>
