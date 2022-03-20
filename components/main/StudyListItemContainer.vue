<template>
  <div class='list-total-container'>
    <div v-for='(d,i) in data' :key='i'>
      <div class='list-total-sub-container'>
        <study-list-item :title='d.first'></study-list-item>
        <study-list-item :title='d.second'></study-list-item>
      </div>
      <div class='mid-line'></div>
    </div>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import StudyListItem from '~/components/main/StudyListItem'

export default {
  name: 'StudyListItemContainer',
  components: { StudyListItem },
  setup() {
    const data = ref([{
      first: 'FRONTEND', second: 'PROGRAM\n' +
        '-MING \n' +
        'LANGUAGE'
    }, {
      first: 'BACK\n' + 'END', second: 'DATA\n' + 'BASE'
    }])

    return {
      data
    }
  }
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
