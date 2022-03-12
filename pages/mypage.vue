<template>
  <div class='mypage-container'>
    <tab-header :lists='list' @tabChange='showThing'></tab-header>
    <div v-if='tab===0'>
      <my-profile-container></my-profile-container>
    </div>
    <div v-else>
      <setting-container></setting-container>
    </div>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import TabHeader from '~/components/parts/Tab'
import MyProfileContainer from '~/components/mypage/MyProfileContainer'
import SettingContainer from '~/components/mypage/SettingContainer'

export default {
  name: 'MyPage',
  components: { SettingContainer, MyProfileContainer, TabHeader },
  setup() {
    const list = ['내 프로필', '설정']
    const tab = ref(0)
    const showThing = (t) => {
      tab.value = t
    }
    return { list, showThing, tab }
  }
}
</script>

<style scoped>
.mypage-container {
  margin-top: 7.9vh;
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>
