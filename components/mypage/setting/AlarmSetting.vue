<template>
  <div class='alarm-container'>
    <profile-title>
      <template #title>알람 설정</template>
    </profile-title>
    <div class='alarm-container-description'>알람 관련 설명 알람 관련 설명 알람 관련 설명 알람 관련 설명 알람 관련</div>
    <div class='alarm-items-container'>
      <span>총 2개의 스터디</span>
      <div
        v-for='(list, idx) in lists' :key='idx' :class='{"item-checked": checked.includes(list)}' class='alarm-items'
        @click='check(idx)'>
        <icon-check :setting-selected='checked.includes(list)'></icon-check>
        <div class='alarm-items-item'>{{ list }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import IconCheck from 'assets/svg/IconCheck'
import { ref } from '@nuxtjs/composition-api'
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'

export default {
  name: 'AlarmSetting',
  components: { IconCheck, ProfileTitle },
  setup() {
    const lists = ['슈퍼하드 Processing Study', '알고리즘 스터디']
    const checked = ref(lists)
    const check = (list) => {
      if (checked.value.includes(list)) {
        const id = checked.value.indexOf(list)
        checked.value.splice(id, 1)
      } else {
        checked.value.push(list)
      }
    }
    return {
      lists, check,
      checked
    }
  }
}
</script>

<style lang='scss' scoped>
.alarm-container {
  display: flex;
  flex-direction: column;
  border-bottom: 1px solid $grey-3;

  &-description {
    font-size: $kor-p3;
    color: $grey-4;
    font-weight: 500;
    margin-top: 0.8vh;
  }
}

.alarm-items {
  display: flex;
  color: $grey-4;
  align-items: center;
  margin-top: 1.85vh;

  &-container {
    position: relative;
    display: flex;
    flex-direction: column;
    left: 1.875vw;
    margin-top: 4vh;
    margin-bottom: 5.18vh;

    span {
      font-family: "Chakra Petch", sans-serif;
      font-size: $kor-p5;
      color: $grey-4;
    }
  }

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
