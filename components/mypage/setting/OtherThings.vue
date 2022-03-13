<template>
  <div class='things-container'>
    <div class='policy item'>이용약관</div>
    <div class='member'>
      <div class='item'>로그아웃</div>
      <div class='item out'>회원탈퇴</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'OtherThings'
}
</script>

<style lang='scss' scoped>
.things-container {
  margin-top: 7.4vh;
  display: flex;
  flex-direction: column;
  font-size: $eng-h3;
  font-weight: 600;
  width: 30.4vw;
  margin-bottom: 19.5vh;
}

.item {
  //padding: 1vh 0.88vw;
  display: inline;
}

.policy {
  display: inline;
}

.member {
  display: flex;
  margin-top: 5.9vh;
}

.out {
  margin-left: 12.7vw;
}
</style>
