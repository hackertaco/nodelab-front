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
          <div class='header-button' @click='toggleSideBar'>
            <icon-menu></icon-menu>
          </div>
        </div>
      </div>
    </div>
    <div v-if='isSideBarOpened' class='sidebar-container'>
      <div class='sidebar-background theOther-container' @click='toggleSideBar'></div>
      <div class='sidebar-contents'>
        <div @click='toggleSideBar'>
          <icon-close class='sidebar-close' height='1.5vh' width='1.5vw'></icon-close>
        </div>
        <div class='sidebar-contents-body'>
          <div class='sidebar-contents-body-card'>
            <icon-star class='card-icon'></icon-star>
            <span class='card-title'>내 닉네임</span>
            <span class='card-mypage'>마이페이지</span>
          </div>
          <div class='sidebar-contents-body-button'>
            <icon-logo class='icon' color='#6CF080' height='1.4vh' width='0.9vw'></icon-logo>
            <span class='mint'>스터디 만들어 보지 않을래요?</span>
          </div>
          <div class='sidebar-contents-body-button margin60'>
            <icon-logo class='icon' height='1.4vh' width='0.9vw'></icon-logo>
            <span>내 스터디 바로가기</span>
          </div>
          <span class='sidebar-contents-body-items'>전체 스터디</span>
          <span class='sidebar-contents-body-items'>북마크, 완료 스터디</span>
          <span class='sidebar-contents-body-items'>노드랩에 문의하기</span>
          <span class='sidebar-contents-body-items logout'>로그아웃</span>
        </div>

      </div>
    </div>
    <div v-if='isSearching' class='recommend-container'>
      <recommend-container></recommend-container>
    </div>
    <div v-if='isSearching' class='theOther-container z-idx-theOther' @click='isSearching=false'></div>
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
import IconClose from 'assets/svg/IconClose'
import IconStar from 'assets/svg/IconStar'
import IconLogo from 'assets/svg/IconLogo'
import RecommendContainer from '~/components/header/RecommendContainer'

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'default.vue',
  components: { IconLogo, IconStar, IconClose, RecommendContainer, IconPrev, IconMenu, IconSearch },
  setup() {
    const isSearching = ref(false)
    const isSideBarOpened = ref(false)
    const toggleBtn = () => {
      isSearching.value = !isSearching.value
    }
    const toggleSideBar = () => {
      isSideBarOpened.value = !isSideBarOpened.value
    }

    return {
      isSearching, toggleBtn, toggleSideBar, isSideBarOpened
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

}

.theOther-container {
  width: 100%;
  position: fixed;
  background: rgba(141, 141, 141, 0.9);
  height: 100vh;
}

.z-idx-theOther {
  z-index: 98;
}

.sidebar-container {
  width: 100%;
  height: 100vh;
  z-index: 101;
  display: flex;

  .sidebar-background {
    top: 0;
  }

  .sidebar-contents {
    width: 24vw;
    height: 100vh;
    background-color: #FAFAFA;
    position: fixed;
    right: 0;
    top: 0;
    display: flex;
    flex-direction: column;
    align-items: center;


    &-body {
      width: 20.2vw;

      position: relative;
      top: 7.4vh;

      &-card {
        width: 100%;
        background-color: #FFFFFF;
        border: 0.5px solid $grey-3;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin-bottom: 2.4vh;

        .card-icon {
          margin-top: 4vh;
        }

        .card-title {
          font-size: $kor-20;
          font-weight: bold;
          color: $dark-191919;
          margin-top: 1.8vh;

        }

        .card-mypage {
          color: $grey-4;
          font-size: $eng-h4;
          font-weight: 500;
          margin-top: 0.8vh;
          margin-bottom: 3.6vh;
        }
      }

      &-button {
        width: 100%;
        background-color: $dark-191919;
        display: flex;
        align-items: center;
        height: 5.9vh;
        margin-bottom: 2.2vh;

        span {
          font-size: $kor-20;
          color: $background;
          margin-left: 0.9vw;
          position: relative;
        }

        .mint {
          color: $mint;
        }

        .icon {
          margin-left: 2.2vw;
          position: relative;
        }
      }

      &-items {
        font-size: $kor-20;
        color: $dark-191919;
        position: relative;
        left: 2.9vw;
        font-weight: bold;
        display: block;
        margin-bottom: 3.6vh;
      }

    }

  }

  .margin60 {
    margin-bottom: 5.5vh;
  }

  .sidebar-close {
    position: absolute;
    top: 1.9vh;
    right: 1vw;
    cursor: pointer;
  }

  .logout {
    top: 21vh;
  }
}
</style>
