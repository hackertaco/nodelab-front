<template>
  <div class='footer-container'>
    <div class='footer-square'></div>
    <div class='footer-contents'>
      <span class='footer-first'>서비스 이용약관</span>
      <span class='footer-first'>개인정보 처리방침</span>
      <div class='colored'>
        <div class='colored-title'>단체명</div>
        <span>노드랩</span></div>
      <div class='colored'>
        <div class='colored-title'>대표자</div>
        <span>이재규</span>
      </div>
      <span class='footer-mail'>asdfqwer1234@gmail.com</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FooterContainer'
}
</script>

<style lang='scss' scoped>
.footer-container {
  border-top: 2px solid $grey-2;
  width: 100%;
  position: relative;
  height: 10vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.footer-square {
  width: 40px;
  height: 12px;
  position: absolute;
  right: 0;
  top: 0;
  background-color: $grey-2;
}

.footer-contents {
  font-size: $kor-p5;
  position: relative;
  display: flex;
  width: 62.5%;

  span {
    color: $grey-4;
  }

  .colored {
    display: flex;
    margin-left: 8%;
    width: 13%;

    .colored-title {
      color: $grey-3;
      margin-right: 3%;
    }
  }

  .footer-first {
    //margin-right: 10%;
    width: 22%;
  }

  .footer-mail {
    margin-left: 12%;
  }
}
</style>
