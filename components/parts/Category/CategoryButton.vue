<template>
  <div class='item'>
    <div :class='`${isListOpened? "btn-clicked" : "btn-no-click"}`' class='btn' @click='toggleList'>카테고리</div>
    <div class='line'></div>
    <category-list-container v-if='isListOpened'></category-list-container>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import CategoryListContainer from '~/components/parts/Category/CategoryListContainer'

export default {
  name: 'CategoryButton',
  components: { CategoryListContainer },
  setup() {
    const isListOpened = ref(false)
    const toggleList = () => {
      isListOpened.value = !isListOpened.value
    }
    return {
      toggleList,
      isListOpened
    }
  }
}
</script>

<style lang='scss' scoped>
.item {
  display: flex;
  flex-direction: column;
  margin-right: 1.25vw;
  align-content: center;
  cursor: pointer;

  .btn {
    width: 6vw;
    height: 4vh;
    margin-bottom: 5px;
    font-size: $kor-20;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .btn-clicked {
    color: #F7F7F7;
    background-color: $dark-191919;
  }

  .btn-no-click {
    background-color: $grey-1;
    color: $grey-4;
  }

  .line {
    border-bottom: 1px solid #E5E5E5;
    width: 6vw;
  }
}

//.item:hover {
//
//  .btn {
//    color: $pink;
//    font-weight: bold;
//    margin-bottom: 0;
//  }
//
//  .line {
//    border-bottom: 1px solid $pink;
//  }
//}
</style>
