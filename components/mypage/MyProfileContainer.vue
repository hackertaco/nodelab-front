<template>
  <div class='contents profile-container'>
    <div class='profile-title-container'>
      <icon-profile></icon-profile>
      <span class='profile-title'>닉네임</span>
      <span class='profile-id'>가입 아이디</span>
    </div>
    <div class='profile-contents'>
      <accomplishment-container class='profile-contents-common'></accomplishment-container>
      <position-container class='profile-contents-common'></position-container>
      <interest-container class='profile-contents-common'></interest-container>
      <github-url class='profile-contents-common'></github-url>
      <introduce-container class='profile-contents-other-margin'></introduce-container>
      <button-container class='footer-margin'>
        <template #btnName>
          프로필 수정
        </template>
      </button-container>
    </div>

  </div>
</template>

<script>
import IconProfile from 'assets/svg/IconProfile'
import AccomplishmentContainer from '~/components/mypage/profile/Accomplishment'
import PositionContainer from '~/components/mypage/profile/Position'
import InterestContainer from '~/components/mypage/profile/Interest'
import GithubUrl from '~/components/mypage/profile/GithubUrl'
import IntroduceContainer from '~/components/mypage/profile/Introduce'
import ButtonContainer from '~/components/parts/Button'

export default {
  name: 'MyProfileContainer',
  components: {
    ButtonContainer,
    IntroduceContainer,
    GithubUrl,
    InterestContainer,
    PositionContainer,
    AccomplishmentContainer,
    IconProfile
  }
}
</script>

<style lang='scss' scoped>
.profile-container {
  margin-top: 9.3vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.profile-id {
  font-size: $kor-p3;
  font-weight: 500;
  margin-top: 1.5vh;
}

.profile-title {
  font-size: $kor-36;
  font-weight: bold;
  margin-top: 3.2vh;

  &-container {
    width: 9.0vw;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

.profile-contents {
  width: 30.4vw;
  margin-top: 6vh;

  &-common {
    margin-bottom: 5.9vh;
  }

  &-other-margin {
    margin-bottom: 4.5vh;
  }
}

.footer-margin {
  margin-bottom: 27.5vh;
}
</style>
