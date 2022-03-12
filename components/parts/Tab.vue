<template>
  <div class='tab-container contents'>
    <div class='tab-container-buttons'>
      <div
        v-for='(list, index) in lists' :key='index' :class='{"tab-button": index === currentTab}' class='tab-common'
        @click='changeTab(index)'>
        <span :class='{"selected":index === currentTab, "notSelected":index !== currentTab}'>{{ list }}</span>
        <div
          :class='{"rectangular-selected": index === currentTab,"rectangular-notSelected" : index !== currentTab}'
          class='rectangular '></div>
      </div>
    </div>
    <divider-line color='grey'></divider-line>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import DividerLine from '~/components/parts/Divider'

export default {
  name: 'TabHeader',
  components: { DividerLine },
  props: {
    lists: {
      type: Array
    }
  },
  setup() {
    const currentTab = ref(0)

    // 만약 cT가 0이면, 첫번째 tab의 class가 tab-button이어야 함
    const changeTab = (idx) => {
      currentTab.value = idx
    }
    return {
      currentTab,
      changeTab
    }
  }
}
</script>

<style lang='scss' scoped>
.tab-container {
  display: flex;
  flex-direction: column;

  &-buttons {
    display: flex;
    margin-bottom: -0.35vh;
    font-size: $eng-h3;
  }
}

.tab-button {
  height: 40px;
  border-bottom: 4px solid $dark-191919;
  z-index: 1;
}

.tab-common {
  margin-right: 1.8vw;
  display: flex;
  line-height: 33px;
  cursor: pointer;
}

.rectangular {
  width: 4px;
  height: 4px;
  margin-left: 0.4vw;
  margin-top: 1vh;

}

.rectangular-selected {
  background: $dark-191919 !important;
}

.rectangular-notSelected {
  background: $grey-3;
}

.selected {
  color: #191919;
}

.notSelected {
  color: $grey-3;
}
</style>
