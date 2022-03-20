<template>
  <div class='item'>
    <div :class='`${changeButton()}`' class='btn' @click='toggleList'>{{ categoryName }}
    </div>
    <div :class="categoryName === '카테고리'? 'line': 'line-selected'"></div>
    <category-list-container v-if='isListOpened' @selected='change'></category-list-container>
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
    const categoryName = ref('카테고리')
    const toggleList = () => {
      isListOpened.value = !isListOpened.value
    }
    const change = list => {
      categoryName.value = list
      toggleList()

    }

    const changeButton = () => {
      if (isListOpened.value === true) {
        return 'btn-clicked'
      } else if (categoryName.value === '카테고리') {
        return 'btn-no-click'
      } else {
        return 'btn-no-click-selected'
      }

    }
    return {
      toggleList,
      isListOpened, change, categoryName, changeButton
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

    &-selected {
      background-color: $grey-1;
      color: $pink;
    }
  }

  .line {
    border-bottom: 1px solid #E5E5E5;
    width: 6vw;

    &-selected {
      border-bottom: 1px solid $pink;
      width: 6vw;
    }
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
