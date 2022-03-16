<template>
  <div class='bookmark-container'>
    <tab-header
      :lists='list'
      mode='bookmark' @tabChange='showThing'></tab-header>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import TabHeader from '~/components/parts/Tab'

export default {
  name: 'BookmarkPage',
  components: { TabHeader },
  setup() {
    const list = ['북마크', '완료 스터디']
    const tab = ref(0)
    const showThing = (t) => {
      tab.value = t
    }
    return { list, showThing, tab }
  }
}
</script>

<style scoped>
.bookmark-container {
  margin-top: 10.3vh;
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>
