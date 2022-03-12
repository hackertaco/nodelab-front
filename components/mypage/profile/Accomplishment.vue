<template>
  <div class='acc-container'>
    <div class='acc-title-container'>
      <profile-title>
        <template #title>평균 성취율</template>
      </profile-title>
      <div v-if='!isStudyListOpened' class='study' @click='toggleStudyList'>총 2개의 스터디</div>
      <div v-else class='study' @click='toggleStudyList'>목록 닫기</div>
    </div>
    <div v-if='!isStudyListOpened' class='acc-info'>
      <div class='acc-info-ratio-title'>성취율</div>
      <div class='acc-info-ratio'>80%</div>
    </div>
    <div v-if='!isStudyListOpened' class='acc-ratio'>
      <div class='acc-ratio-real'></div>
    </div>
    <div v-else class='acc-study-list'>
      <div v-for='(list, index) in lists' :key='index' class='acc-study-list-container'>
        <span class='list-title'>{{ list.name }}</span>
        <span class='list-duration'>{{ list.duration }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'

export default {
  name: 'AccomplishmentContainer',
  components: { ProfileTitle },
  setup() {
    const isStudyListOpened = ref(false)
    const toggleStudyList = () => {
      isStudyListOpened.value = !isStudyListOpened.value
    }
    const lists = [
      { name: '슈퍼하드 Processing Study', duration: '20. 10. 01 - 20. 11. 03' },
      { name: '알고리즘 스터디', duration: '20. 11. 22 - 20. 12. 30' }
    ]
    return {
      toggleStudyList,
      isStudyListOpened, lists
    }
  }
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
  cursor: pointer;
}

.acc-study-list {
  background: #FFFFFF;
  border: 1px solid $grey-3;
  width: 100%;
  height: 22.9vh;
  margin-top: 1.3vh;
  font-family: "Chakra Petch", sans-serif;
  display: flex;
  flex-direction: column;
  padding: 2vh 1vw 0 1vw;

  &-container {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1.8vh;
    align-items: center;
  }

}

.list-title {
  font-size: $kor-20;
  font-weight: 500;
}

.list-duration {
  font-size: $kor-p4;
}
</style>
