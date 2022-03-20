<template>
  <div class='item-container'>
    <study-item-body :title='title'>
    </study-item-body>
    <div class='mid-divider'></div>
    <study-item-footer></study-item-footer>
  </div>
</template>

<script>
import StudyItemBody from '~/components/main/StudyItemBody'
import StudyItemFooter from '~/components/main/StudyItemFooter'

export default {
  name: 'StudyListItem',
  components: { StudyItemFooter, StudyItemBody },
  props: {
    title: {
      type: String
    }
  }
}
</script>

<style lang='scss' scoped>
.item-container {
  width: 47%;

  height: 211px;

}

.mid-divider {
  border: 1px solid $grey-2;
  width: 100%;
}
</style>
