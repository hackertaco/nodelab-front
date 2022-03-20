<template>
  <div class='list-container contents'>
    <span
      v-for='(list, index) in lists' :key='index' :class='{"list-item-selected" : selectedItem===list}'
      class='list-item'
      @click='selectOne(list)'>{{ list }}</span>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'

export default {
  name: 'CategoryListContainer',
  setup(_, { emit }) {
    const selectedItem = ref('')
    const lists = ['frontend', 'backend', 'ios', 'android', '알고리즘', 'devops', 'database', '사이드 프로젝트', 'programming language']
    const selectOne = list => {
      selectedItem.value = list
      emit('selected', list)
    }
    return {
      lists,
      selectOne,
      selectedItem
    }
  }
}
</script>

<style lang='scss' scoped>
.list-container {
  background: $grey-1;
  display: flex;
  font-family: "Chakra Petch", sans-serif;
  font-size: $kor-20;
  padding: 4.1vh 3.125vw 0 3.125vw;
  flex-wrap: wrap;
  //width: 100%;
}

.list-item {
  margin-right: 2.5vw;
  list-style: none;
  display: inline;
  margin-bottom: 4.6vh;

  &-selected {
    color: $pink;
  }
}

.list-item:hover {
  color: $pink;
}
</style>
