<template>
  <div class='category-container'>
    <div class='category-count'>총 <span class='team-count'>3</span>개의 팀</div>
    <category-button></category-button>
  </div>
</template>

<script>
import CategoryButton from '~/components/parts/Category/CategoryButton'

export default {
  name: 'CategoryContainer',
  components: { CategoryButton }
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
