<template>
  <div class='receive-container'>
    <profile-title>
      <template #title>수신 설정</template>
    </profile-title>
    <div class='receive-container-description'>알람 관련 설명 알람 관련 설명 알람 관련 설명 알람 관련 설명 알람 관련</div>
    <div :class='{"item-checked": checked===true}' class='receive-items' @click='check'>
      <icon-check :setting-selected='checked===true'></icon-check>
      <div class='receive-items-item'>E - mail</div>
    </div>
  </div>
</template>

<script>
import IconCheck from 'assets/svg/IconCheck'
import { ref } from '@nuxtjs/composition-api'
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'

export default {
  name: 'ReceiveSetting',
  components: { IconCheck, ProfileTitle },
  setup() {
    const checked = ref(true)
    const check = () => {
      checked.value = !checked.value
    }
    return {
      checked, check
    }
  }
}
</script>

<style lang='scss' scoped>
.receive-container {
  display: flex;
  flex-direction: column;
  border-bottom: 1px solid $grey-3;
  margin-top: 5.1vh;

  &-description {
    font-size: $kor-p3;
    color: $grey-4;
    font-weight: 500;
    margin-top: 0.8vh;
  }
}

.receive-items {
  position: relative;
  display: flex;
  left: 1.875vw;
  margin-top: 4vh;
  margin-bottom: 5.18vh;
  cursor: pointer;

  &-item {
    font-family: "Chakra Petch", sans-serif;
    font-size: $kor-20;
    font-weight: 500;
    margin-left: 1vw;
  }
}

.item-checked {
  color: $dark-191919;
  font-weight: bold;
}
</style>
