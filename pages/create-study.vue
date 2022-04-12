<template>
  <div class='create-study-container'>
    <tab-header :lists='list' @tabChange='showThing'></tab-header>
    <div class='contents create-study-contents-container'>
      <input v-model='type' class=' create-study-title ' placeholder='스터디 이름을 정해주세요!' @input='checkType' />
      <div v-if='showWarning' class='warning'>스터디 이름은 30자를 넘을 수 없습니다!</div>
      <div class='create-study-info-container'>
        <div class='create-study-info-count create-study-info '>
          <div class='create-study-info-count-title'>스터디 인원</div>
          <div>
            <span @click='deductCount'>-</span>
            <span class='count'>{{ count }}</span>
            <span @click='addCount'>+</span>
          </div>
        </div>
        <div class='create-study-info-calendar create-study-info ' @click='openCalendar'>
          <div class='create-study-info-calendar-title'>스터디 기간</div>
          <div>
            <span>22. 03. 03</span>
            <span class='line'>-</span>
            <span>22. 03. 10</span>
          </div>
        </div>

        <div v-if='isCalendarOpen' class='calendar-container'>
          <div @click='toggleCalendar'>
            <icon-close class='calendar-container-icon' height='13px' width='13px'></icon-close>
          </div>
          <calendar-container></calendar-container>
        </div>
      </div>
      <div class='create-study-category-container'>
        <div class='item'>
          <div class='btn'>카테고리</div>
          <div class='line'></div>
        </div>
        <div class='item'>
          <div class='btn btn_input'><input placeholder='초보자, 모두환영 등등 태그로 우리 팀을 소개해 보세요.' /></div>
          <div class='line'></div>
        </div>
      </div>
      <div class='create-study-announce-container'>
        <leader-profile class='create-study-profile'></leader-profile>
        <introduce-study class='create-study-introduce'></introduce-study>
      </div>
      <div class='create-study-noti-container'>
        <div class='create-study-noti-title'>공지사항</div>
        <introduce-study class='create-study-noti-textarea'></introduce-study>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import IconClose from 'assets/svg/IconClose'
import TabHeader from '~/components/parts/Tab'
import CalendarContainer from '~/components/study/create/Calendar'
import LeaderProfile from '@/components/study/create/LeaderProfile'
import IntroduceStudy from '@/components/study/create/IntroduceStudy'

export default {
  name: 'CreateStudy',
  components: { IntroduceStudy, LeaderProfile, CalendarContainer, IconClose, TabHeader },
  setup() {
    const list = ['스터디룸']
    const tab = ref(0)
    const showThing = (t) => {
      tab.value = t
    }
    const type = ref('')
    const showWarning = ref(false)
    const checkType = () => {
      console.log(type.value.length)
      if (type.value.length > 30) {
        showWarning.value = true
      } else {
        showWarning.value = false
      }

    }
    const count = ref(2)
    const addCount = () => {
      count.value += 1
    }
    const deductCount = () => {
      if (count.value !== 2) {

        count.value -= 1
      }
    }
    const isCalendarOpen = ref(false)
    const openCalendar = () => {
      isCalendarOpen.value = true
    }
    const toggleCalendar = () => {
      isCalendarOpen.value = !isCalendarOpen.value
    }
    return {
      list,
      showThing,
      checkType,
      type,
      showWarning,
      count,
      addCount,
      deductCount,
      isCalendarOpen,
      openCalendar,
      toggleCalendar
    }
  }
}
</script>

<style lang='scss' scoped>
.create-study-container {
  margin-top: 7.9vh;
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
}

.create-study-contents-container {
  display: flex;
  flex-direction: column;

}

.create-study-title {
  height: 5vh;
  border-bottom: 1px solid $grey-3;
  margin-top: 1.68vh;
  //position: absolute;
  background-color: #FAFAFA;
  //font-size: $kor-p1;
  font-weight: 600;
}

input::placeholder {
  font-size: $eng-30;
  font-weight: 600;
  color: $grey-4;
  margin-top: 5px;
  line-height: 2;
}

input:focus {
  outline: none;
}

input:active {
  font-size: $eng-30;
  font-weight: 600;
  color: $grey-4;
}

.warning {
  font-size: $kor-14;
  font-weight: 700;
  line-height: 1.5;
  color: $red;
}

.create-study-category-container {
  width: 100%;
  margin-top: 36px;
}

.create-study-info-container {
  display: flex;
  font-family: "Chakra Petch", sans-serif;
  color: $dark-191919;
  margin-top: 1.85vh;
}

.create-study-info {
  font-size: $eng-24;
  font-weight: 600;
  margin-top: 3.8vh;

  &-count {
    display: flex;
    width: 25%;
    flex-grow: 1;

    &-title {
      width: 8.7vw;
      margin-right: 0.83vw;
    }

    .count {
      margin: 0 1.5vw;
    }
  }

  &-calendar {
    display: flex;
    flex-grow: 1;
    width: 25%;
    position: relative;
    cursor: pointer;

    &-title {
      margin-right: 2.39vw;
    }

    .line {
      margin: 0 1.5vw;
    }
  }
}

.calendar-container {
  width: 31.35vw;
  height: 34.6vh;
  background-color: #fff;
  border: 0.5px solid $grey-3;
  position: absolute;
  display: flex;
  align-items: center;
  margin-top: 46px;
  left: 50%;
  justify-content: center;

  &-icon {
    right: 17px;
    top: 17px;
    position: absolute;
    cursor: pointer;
  }
}

.create-study-announce-container {
  width: 100%;
  justify-content: space-between;
  display: flex;
  margin-top: 3.7vh;
}

.create-study-profile {
  width: 31.5%;
  height: 26.3vh;
}

.create-study-introduce {
  width: 65.75%;
  height: 26.3vh;
}

.create-study-noti-container {
  width: 100%;
  height: 19.5vh;
  display: flex;
  flex-direction: column;
  margin-top: 5.5vh;
  justify-content: space-between;
  margin-bottom: 96px;
}

.create-study-noti-title {
  font-weight: 600;
  font-size: $eng-24;
  line-height: 1.3;
  letter-spacing: -0.03em;
  height: 1.61%;
  /* dark_#191919 */

  color: #191919;
}

.create-study-noti-textarea {
  width: 100%;
  height: 76.3%;

}

.item {
  display: flex;
  flex-direction: column;
  align-content: center;
  cursor: pointer;
  height: 50px;

  .btn {
    background-color: $grey-1;
    width: 6vw;
    height: 4vh;
    margin-bottom: 5px;
    font-size: $kor-20;
    color: $grey-4;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .btn input {
    width: 90%;
    height: 80%;
    background-color: $grey-1;
    font-weight: 500;
    font-size: $kor-20;
    line-height: 1.5;


  }

  .btn input::placeholder {
    color: $grey-4;
    font-size: $kor-20;
    font-weight: 400;
  }

  .btn_input {
    width: 41.75% !important;
    height: 4vh;
    display: flex;
    justify-content: center;
    align-items: center;

  }

  .line {
    border-bottom: 1px solid #E5E5E5;
    width: 6vw;
  }

  .create-study-category-container {
    width: 100%
  }
}
</style>
