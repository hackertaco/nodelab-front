<template>
  <div class='calendar-main-container'>
    <div class='calendar-left'>
      <div class='calendar-title'>
        <icon-prev class='icon-left' height='16' width='10'></icon-prev>
        {{ year }}.{{ month }}
      </div>
      <div class='num'><span v-for='(d, i) in days' :key='i' :class='{ "red": d==="일"}' class='cal-item'>{{ d }}</span>
      </div>
      <div class='num'>
        <span
          v-for='(l, i) in leftC' :key='i' :class='{"checked": isChecked(i, "left"), "between": isBetween(i, "left")}'
          class='cal-item'
          @click='checkDay(i, "left")'>{{ l }}</span>
      </div>
    </div>
    <div class='calendar-right'>
      <div class='calendar-title right '>
        {{ year }}.{{ nextMonth }}
        <icon-next class='icon-right'></icon-next>
      </div>
      <div class='num'><span v-for='(d, i) in days' :key='i' :class='{ "red": d==="일"}' class='cal-item'>{{ d }}</span>
      </div>
      <div class='num'>
        <span
          v-for='(l, j) in rightC' :key='j'
          :class='{"checked": isChecked(j, "right"), "between": isBetween(j, "right")}'
          class='cal-item' @click='checkDay(j, "right")'>{{ l }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import IconPrev from 'assets/svg/IconPrev'
import IconNext from 'assets/svg/IconNext'
import { ref } from '@nuxtjs/composition-api'

export default {
  name: 'CalendarContainer',
  components: { IconNext, IconPrev },
  setup() {
    const date = new Date()
    const year = date.getFullYear()
    const getMonth = (month) => {
      if (month < 10) {
        return `0${month}`
      } else if (month === 11) {
        return '01'
      } else {
        return month
      }
    }
    const month = getMonth(date.getMonth() + 1)
    const nextMonth = getMonth(parseInt(month, 10) + 1)
    const parsedMonth = (month) => {
      if (month === 0) {
        return 11
      } else {
        return month
      }
    }
    const parsed = new Date(year, parsedMonth(parseInt(month, 10) - 1)).getDay()
    console.log((parseInt(month, 10)), parsed)

    const leftC = Array.from({ length: 30 }, (v, i) => i + 1)
    const rightC = Array.from({ length: 31 }, (v, i) => i + 1)
    const days = ['일', '월', '화', '수', '목', '금', '토']
    const firstChecked = ref({ idx: -1 })
    const secondChecked = ref({ idx: -1 })
    const checkDay = (idx, direction) => {
      if (secondChecked.value.idx !== -1) {
        // 둘 다 초기화
        firstChecked.value.idx = -1
        secondChecked.value.idx = -1
      }
      if (firstChecked.value.idx === -1) {
        firstChecked.value.idx = idx
        firstChecked.value.direction = direction
      } else {
        secondChecked.value.idx = idx
        secondChecked.value.direction = direction
        console.log(secondChecked.value)
      }
    }
    const isChecked = (i, direction) => {
      return (i === firstChecked.value.idx && direction === firstChecked.value.direction) || (i === secondChecked.value.idx && direction === secondChecked.value.direction)
    }
    const isBetween = (i, direction) => {
      if (secondChecked.value.idx !== -1) {
        if (secondChecked.value.direction !== firstChecked.value.direction) {

          if (direction === 'left') {
            return i > firstChecked.value.idx
          } else {
            console.log(i < secondChecked.value.idx)
            return i < secondChecked.value.idx
          }
        } else {
          return (i > firstChecked.value.idx && i < secondChecked.value.idx) && direction === secondChecked.value.direction

        }
      }
    }
    return { leftC, days, checkDay, firstChecked, secondChecked, rightC, year, month, nextMonth, isChecked, isBetween }
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
}

.icon-left {
  margin-right: 12px;
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
