<template>
  <div class='category-container'>
    <div class='category-count'>총 <span class='team-count'>3</span>개의 팀</div>
    <category-button></category-button>
    <study-list-item-container></study-list-item-container>
  </div>
</template>

<script>
import CategoryButton from '~/components/parts/Category/CategoryButton'
import StudyListItemContainer from '~/components/main/StudyListItemContainer'

export default {
  name: 'CategoryContainer',
  components: { StudyListItemContainer, CategoryButton }
}
</script>

<style lang='scss' scoped>
.category-container {
  color: $grey-4;
  display: flex;
  flex-direction: column;
}

.category-count {
  font-size: $kor-16;
  margin-bottom: 2.4vh;
}

.team-count {
  color: $dark-191919;
  font-family: "Chakra Petch", sans-serif;
}
</style>
