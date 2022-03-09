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
      <recommend-container></recommend-container>
    </div>
    <div v-if='isSearching' class='theOther-container' @click='isSearching=false'></div>
    <Nuxt />
  </div>
</template>

<script>
import IconSearch from 'assets/svg/IconSearch'
import IconMenu from 'assets/svg/IconMenu'
import IconPrev from 'assets/svg/IconPrev'
import { ref } from '@nuxtjs/composition-api'
// import IconStar from 'assets/svg/IconStar'
// import DividerLine from '~/components/parts/Divider'
import RecommendContainer from '~/components/header/RecommendContainer'

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'default.vue',
  components: { RecommendContainer, IconPrev, IconMenu, IconSearch },
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
  height: 6vh;
  background-color: #FAFAFA;
  position: sticky;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  z-index: 100;
  border-bottom: 1px solid #C4C4C4;

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
  font-size: $eng-h2;
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
  height: 32.6vh;
  background-color: #FAFAFA;
  position: fixed;
  z-index: 99;
  display: flex;
  justify-content: center;
  top: 6vh;

  //.recommend-contents {
  //  width: 62.5%;
  //  display: flex;
  //  flex-direction: column;
  //
  //  .divider {
  //    margin-bottom: 6vh;
  //  }
  //
  //  .recommend-category {
  //    display: flex;
  //
  //    .item {
  //      display: flex;
  //      flex-direction: column;
  //      margin-right: 1.25vw;
  //      align-content: center;
  //      cursor: pointer;
  //
  //      .btn {
  //        background-color: $grey-1;
  //        width: 6vw;
  //        height: 4vh;
  //        margin-bottom: 5px;
  //        font-size: $kor-20;
  //        color: $grey-4;
  //        display: flex;
  //        align-items: center;
  //        justify-content: center;
  //      }
  //
  //      .line {
  //        border-bottom: 1px solid #E5E5E5;
  //      }
  //    }
  //
  //    .item:hover {
  //
  //      .btn {
  //        color: $pink;
  //        font-weight: bold;
  //        margin-bottom: 0;
  //      }
  //
  //      .line {
  //        border-bottom: 1px solid $pink;
  //      }
  //    }
  //  }
  //
  //  .recommend-title {
  //    display: flex;
  //    align-items: center;
  //    position: relative;
  //    top: 4vh;
  //    margin-bottom: 6vh;
  //
  //    span {
  //      margin-left: 0.9vw;
  //      font-size: $kor-36;
  //      line-height: 49px;
  //      font-weight: bold;
  //    }
  //
  //    .rectangular {
  //      width: 8px;
  //      height: 8px;
  //      background-color: $dark-191919;
  //      margin-top: 7px;
  //      margin-left: 0.2vw;
  //      position: relative;
  //      bottom: 25%;
  //    }
  //  }
  //
  //}
}

.theOther-container {
  width: 100%;
  position: fixed;
  background: rgba(141, 141, 141, 0.9);
  height: 100vh;
  z-index: 98;

}
</style>
