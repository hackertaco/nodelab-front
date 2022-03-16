<template>
  <div class='tab-container contents'>
    <div :class='`font-${mode}`' class='tab-container-buttons'>
      <div
        v-for='(list, index) in lists' :key='index' :class='{"tab-button": isSelected(index)}' class='tab-common'
        @click='changeTab(index)'>
        <span :class='{"selected":isSelected(index), "notSelected":!isSelected(index)}'>{{ list }}</span>
        <rectangular-point :is-selected='isSelected(index)' :mode='mode'></rectangular-point>
      </div>
    </div>
    <divider-line color='grey'></divider-line>
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import DividerLine from '~/components/parts/Divider'
import RectangularPoint from '~/components/parts/RectangularPoint'

export default {
  name: 'TabHeader',
  components: { RectangularPoint, DividerLine },
  props: {
    lists: {
      type: Array
    },
    mode: {
      type: String,
      default: 'mypage'
    }
  },
  setup(props, { emit }) {
    const currentTab = ref(0)

    // 만약 cT가 0이면, 첫번째 tab의 class가 tab-button이어야 함
    const changeTab = (idx) => {
      currentTab.value = idx
      emit('tabChange', currentTab.value)
    }
    const isSelected = idx => (idx === currentTab.value)
    return {
      currentTab,
      changeTab,
      isSelected
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
  }
}

.font-mypage {
  font-size: $eng-24;
  line-height: 33px;
}

.font-bookmark {
  font-size: $kor-36;
  line-height: 20px;
}

.tab-button {
  height: 40px;
  border-bottom: 4px solid $dark-191919;
  z-index: 1;
}

.tab-common {
  margin-right: 1.8vw;
  display: flex;

  cursor: pointer;
}


.selected {
  color: #191919;
  font-weight: bold;
}

.notSelected {
  color: $grey-3;
}
</style>
