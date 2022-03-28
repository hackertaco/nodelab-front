<template>
  <div class='calendar-main-container'>
    <div class='calendar-left'>
      <div class='calendar-title'>
        <icon-prev class='icon-left' height='16' width='10'></icon-prev>
        2021.06
      </div>
      <div class='num'><span v-for='(d, i) in days' :key='i' :class='{ "red": d==="일"}'>{{ d }}</span></div>
      <div class='num'>
        <span v-for='(l, i) in leftC' :key='i'>{{ l }}</span>
      </div>
    </div>
    <div class='calendar-right'>
      <div class='calendar-title right '>
        2021.07
        <icon-next class='icon-right'></icon-next>
      </div>
      <div class='num'><span v-for='(d, i) in days' :key='i' :class='{ "red": d==="일"}'>{{ d }}</span></div>
      <div class='num'>
        <span v-for='(l, i) in leftC' :key='i'>{{ l }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import IconPrev from 'assets/svg/IconPrev'
import IconNext from 'assets/svg/IconNext'

export default {
  name: 'CalendarContainer',
  components: { IconNext, IconPrev },
  setup() {
    const leftC = Array.from({ length: 30 }, (v, i) => i + 1)
    const days = ['일', '월', '화', '수', '목', '금', '토']
    return { leftC, days }
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

  gap: 8px 10px;
  margin-top: 20px;
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
</style>
