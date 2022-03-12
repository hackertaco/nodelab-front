<template>
  <div class='list-container'>
    <div
      v-for='(l, index) in list' :key='index' :class='{"list-checked": checked.includes(l)}' class='list-item'
      @click='checkList(l)'>
      {{ l.toUpperCase() }}
    </div>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'

export default {
  name: 'SelectList',
  setup() {
    const list = ['frontend', 'backend', 'fullstack', 'devops', 'manager', 'mobile', 'ai', 'data', 'database']
    const checked = ref([])
    const checkList = l => {
      if (checked.value.includes(l)) {
        const idx = checked.value.indexOf(l)
        checked.value.splice(idx, 1)
      } else {
        checked.value.push(l)
      }
    }

    return {
      list, checkList, checked
    }
  }
}
</script>

<style lang='scss' scoped>
.list-container {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  color: $grey-3;
  font-weight: 500;
  font-family: "Chakra Petch", sans-serif;
  font-size: $kor-20;
}

.list-item {
  margin-right: 1.25vw;
  margin-top: 2vh;
  cursor: pointer;
}

.list-checked {
  color: $dark-191919;
  font-weight: 600;
}
</style>
