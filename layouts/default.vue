<template>
  <div class='total-container'>
    <div class='header-container'>
      <div class='practical-container'>
        <span class='logo-title'>nodelab</span>
        <div class='icon' @click='toggleBtn'>
          <icon-search v-if='!isSearching' height='22' width='22'></icon-search>
          <icon-prev v-else height='22' width='22'></icon-prev>
        </div>
        <input v-if='isSearching' class='title' placeholder='어떤 스터디를 찾으세요?' type='text' />
        <div class='button-container'>
          <div class='header-name'>내 스터디</div>
          <div class='header-button'>
            <icon-menu></icon-menu>
          </div>
        </div>
      </div>
    </div>
    <div v-if='isSearching' class='recommend-container'>
      <div>추천 카테고리</div>
    </div>
    <div v-if='isSearching' class='theOther-container'></div>
    <Nuxt />
  </div>
</template>

<script>
import IconSearch from 'assets/svg/IconSearch'
import IconMenu from 'assets/svg/IconMenu'
import IconPrev from 'assets/svg/IconPrev'
import { ref } from '@nuxtjs/composition-api'

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'default.vue',
  components: { IconPrev, IconMenu, IconSearch },
  setup() {
    const isSearching = ref(false)
    const toggleBtn = () => {
      isSearching.value = !isSearching.value
    }

    return {
      isSearching, toggleBtn
    }
  }
}
</script>

<style lang='scss' scoped>
.total-container {
  display: flex;
  flex-direction: column;
}

.header-container {
  width: 100%;
  height: 64px;
  background-color: #FAFAFA;
  position: sticky;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  z-index: 100;

}

.practical-container {
  width: 62.5%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo-title {
  font-family: "Chakra Petch", sans-serif !important;
  font-weight: 500;
  font-size: $eng-h3;
  display: inline;
  font-style: normal;
}

.icon {
  position: absolute;
  margin-left: 122px;
  cursor: pointer;
}

.title {
  width: 300px;
  height: 100%;
  margin-left: 161px;
  position: absolute;
  background-color: #FAFAFA;
  font-size: $kor-p1;
  font-weight: 600;
}

input::placeholder {
  font-size: $kor-p1;
  font-weight: 600;
  color: $grey-3;
  margin-top: 5px;
}

input:focus {
  outline: none;
}

input[type='text'] {
  font-weight: 600;
  font-family: 'Noto Sans';
}

.button-container {
  width: 25%;
  display: flex;
  height: 100%;
}

.header-name {
  background-color: black;
  color: #FAFAFA;
  font-family: 'Noto Sans KR', sans-serif;
  font-size: $kor-p3;
  width: 63%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.header-button {
  background-color: #F2F2F2;
  height: 100%;
  width: 37%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.recommend-container {
  width: 100%;
  position: relative;
  height: 353px;
  background-color: #FAFAFA;
  border-top: 1px solid #C4C4C4;
  z-index: 99;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.theOther-container {
  width: 100%;
  position: relative;
  background: rgba(141, 141, 141, 0.9);
  height: 100vh;
}
</style>
