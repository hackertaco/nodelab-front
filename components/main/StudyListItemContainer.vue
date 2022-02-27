<template>
  <div class='list-total-container'>
    <div class='list-total-sub-container'>
      <study-list-item></study-list-item>
      <study-list-item></study-list-item>
    </div>
    <div class='mid-line'></div>
    <div class='list-total-sub-container'>
      <study-list-item></study-list-item>
      <study-list-item></study-list-item>
    </div>
    <div class='mid-line'></div>
  </div>
</template>

<script>
import StudyListItem from '~/components/main/StudyListItem'

export default {
  name: 'StudyListItemContainer',
  components: { StudyListItem }
}
</script>

<style lang='scss' scoped>
.list-total-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: 48px;

}

.list-total-sub-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 38px;
}

.mid-line {
  width: 100%;
  background: $grey-1;
  height: 12px;
  margin-bottom: 40px;
}
</style>
