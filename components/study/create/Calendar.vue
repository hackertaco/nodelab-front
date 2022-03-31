<template>
  <div class='calendar-main-container'>
    <div class='calendar-left'>
      <div class='calendar-title' @click='goPrev'>
        <icon-prev class='icon-left' height='16' width='10'></icon-prev>
        {{ year }}.{{ month }}
      </div>
      <div class='num'>

        <span v-for='(d, i) in days' :key='i' :class='{ "red": d==="일"}' class='cal-item'>{{ d }}</span>
      </div>
      <div class='num'>
        <span v-for='(b, idx) in blankLeft' :key='"blank"+idx'>{{ ' ' }}</span>
        <span
          v-for='(l, i) in leftC' :key='i'
          :class='{"checked": isChecked(year, Number(month), i), "between": isBetween(year, Number(month), i)}'
          class='cal-item'
          @click='checkDay(year, Number(month), i)'>{{ l }}</span>
      </div>
    </div>
    <div class='calendar-right'>
      <div class='calendar-title right ' @click='goNext'>
        {{ nextMonth === '01' ? year + 1 : year }}.{{ nextMonth }}
        <icon-next class='icon-right '></icon-next>
      </div>
      <div class='num'><span v-for='(d, i) in days' :key='i' :class='{ "red": d==="일"}' class='cal-item'>{{ d }}</span>
      </div>
      <div class='num'>
        <span v-for='(b, idx) in blankRight' :key='"blankR"+idx'>{{ ' ' }}</span>
        <span
          v-for='(l, j) in rightC' :key='j'
          :class='{"checked": isChecked(nextMonth === "01" ? year + 1 : year, Number(nextMonth), j), "between": isBetween(nextMonth === "01" ? year + 1 : year, Number(nextMonth), j)}'
          class='cal-item' @click='checkDay(nextMonth === "01" ? year + 1 : year, Number(nextMonth), j)'>{{ l }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import IconPrev from 'assets/svg/IconPrev'
import IconNext from 'assets/svg/IconNext'
import { computed, ref } from '@nuxtjs/composition-api'

export default {
  name: 'CalendarContainer',
  components: { IconNext, IconPrev },
  setup() {
    const date = new Date()
    const year = ref(date.getFullYear())

    const getMonth = (month) => {
      if (month < 10) {
        return `0${month}`
      } else {
        return month
      }
    }


    const dateMonth = ref(date.getMonth() + 1) // 3월이라면, 3
    const month = ref(computed(() => getMonth(dateMonth.value)))
    const nextMonth = ref(computed(() => getMonth(dateMonth.value + 1 === 13 ? 1 : dateMonth.value + 1)))
    const blankLeft = ref(computed(() => new Date(year.value, dateMonth.value - 1).getDay()))
    const blankRight = ref(computed(() => new Date(year.value, dateMonth.value).getDay()))
    const leftC = ref(computed(() => Array.from({ length: new Date(year.value, dateMonth.value, 0).getDate() }, (v, i) => i + 1)))
    const rightC = ref(computed(() => Array.from({ length: new Date(year.value, dateMonth.value + 1, 0).getDate() }, (v, i) => i + 1)))

    const goPrev = () => {
      // month가 1씩 줄고
      // 일수가 일씩 줄고
      // secondChecked.value.idx가 first~가
      if (dateMonth.value === 1) {
        year.value -= 1
        dateMonth.value = 12
      } else {
        dateMonth.value -= 1
      }

    }
    const goNext = () => {
      // month가 1씩 줄고
      // 일수가 일씩 줄고
      // secondChecked.value.idx가 first~가
      if (dateMonth.value === 12) {
        year.value += 1
        dateMonth.value = 1
      } else {
        dateMonth.value += 1
      }

    }
    const days = ['일', '월', '화', '수', '목', '금', '토']
    const firstChecked = ref({ year: year.value, month: month.value, day: -1 })
    const secondChecked = ref({ year: year.value, month: nextMonth.value, day: -1 })

    const checkDay = (year, month, day) => {
      if (secondChecked.value.day !== -1) {
        // 둘 다 초기화
        firstChecked.value.day = -1
        secondChecked.value.day = -1
      }

      if (firstChecked.value.day === -1) {
        firstChecked.value.day = day
        firstChecked.value.month = month
        firstChecked.value.year = year
        console.log(firstChecked.value)
      } else {
        secondChecked.value.day = day
        secondChecked.value.month = month
        secondChecked.value.year = year
        if (firstChecked.value.month === secondChecked.value.month && firstChecked.value.day > secondChecked.value.day) {
          console.log('dddd')
          firstChecked.value.day = secondChecked.value.day
          firstChecked.value.month = secondChecked.value.month
          firstChecked.value.year = secondChecked.value.year
          secondChecked.value.day = -1
          secondChecked.value.month = ''
          secondChecked.value.year = ''
          return
        }

        console.log(secondChecked.value)
      }
    }
    const isChecked = (year, month, day) => {
      return (day === firstChecked.value.day && month === firstChecked.value.month && year === firstChecked.value.year)
        || (day === secondChecked.value.day && month === secondChecked.value.month && year === secondChecked.value.year)
    }
    const isBetween = (year, m, day) => {
      if (secondChecked.value.day !== -1) {
        if (secondChecked.value.month !== firstChecked.value.month) {
          // 서로 체크한 달이 다를 때
          if (firstChecked.value.month === m) {
            return day > firstChecked.value.day
          } else if (secondChecked.value.month === m) {
            return day < secondChecked.value.day
          }
        } else {
          return (day > firstChecked.value.day && day < secondChecked.value.day) && m === secondChecked.value.month

        }
      }
    }
    return {
      leftC,
      days,
      checkDay,
      firstChecked,
      secondChecked,
      rightC,
      year,
      month,
      nextMonth,
      isChecked,
      isBetween,
      blankLeft,
      blankRight, goPrev, goNext
    }
  }
}
</script>

<style lang='scss' scoped>
.calendar-main {
  &-container {
    padding: 48px 28px;
    display: flex;
    justify-content: space-between;
    width: 100%;
    height: 100%;
    font-family: "Chakra Petch", sans-serif;
  }


}

.calendar-left {
  //flex-grow: 1;
  width: 44%;

}

.calendar-right {
  //flex-grow: 1;
  width: 44%;
  text-align: right;

}

.num {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  text-align: center;
  font-size: $kor-14;
  vertical-align: middle;
  //gap: 8px 10px;
  margin-top: 10px;

}

.checked {
  background-color: $mint;
}

.between {
  background-color: $lime;
}

.calendar-title {
  font-weight: 600;
  font-size: $eng-24;
  line-height: 1.33;
  display: flex;
  align-items: center;

}

.red {
  color: $red;
}

.right {
  justify-content: right;
}

.icon-right {
  margin-left: 12px;
  cursor: pointer;
}

.icon-left {
  margin-right: 12px;
  cursor: pointer;
}

.cal-item {
  //width: 1.56vw;
  height: 2.7vh;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
</style>
