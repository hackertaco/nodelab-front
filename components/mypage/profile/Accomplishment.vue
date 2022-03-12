<template>
  <div class='acc-container'>
    <div class='acc-title-container'>
      <profile-title>
        <template #title>평균 성취율</template>
      </profile-title>
      <div class='study'>총 2개의 스터디</div>
    </div>
    <div class='acc-info'>
      <div class='acc-info-ratio-title'>성취율</div>
      <div class='acc-info-ratio'>80%</div>
    </div>
    <div class='acc-ratio'>
      <div class='acc-ratio-real'></div>
    </div>
  </div>
</template>

<script>
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'

export default {
  name: 'AccomplishmentContainer',
  components: { ProfileTitle }
}
</script>

<style lang='scss' scoped>
.acc-container {
  display: flex;
  flex-direction: column;
}

.acc-title-container {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.acc-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 3.1vh;

  &-ratio {
    font-size: $eng-h3;
    font-weight: 600;
    font-family: "Chakra Petch", sans-serif;

    &-title {
      font-size: $kor-p4;
      color: $grey-4;
      font-weight: bold;

    }
  }
}

.acc-ratio {
  position: relative;
  background: $grey-1;
  width: 100%;
  height: 2.2vh;
  border-radius: 4px;
  margin-top: 1.3vh;

  &-real {
    height: 2.2vh;
    border-radius: 4px;
    position: relative;
    background: $mint;
    width: 80%;
  }
}

.study {
  color: $grey-4;
  font-size: $kor-20;
}
</style>
