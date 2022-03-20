<template>
  <div class='list-container'>
    <study-list-header :title='title'></study-list-header>
    <divider-line></divider-line>
    <study-list-item-container></study-list-item-container>
  </div>
</template>

<script>
import StudyListHeader from '~/components/main/StudyListHeader'
import DividerLine from '~/components/parts/Divider'
import StudyListItemContainer from '~/components/main/StudyListItemContainer'

export default {
  name: 'StudyListContainer',
  components: { StudyListItemContainer, DividerLine, StudyListHeader },
  props: {
    title: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

<style scoped>
.list-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
</style>
