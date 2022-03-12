<template>
  <div class='introduce-container'>
    <profile-title>
      <template #title>자기소개</template>
    </profile-title>
    <div class='introduce-textarea'>
      <textarea placeholder='팀 지원시 본인을 어필할 메세지를 남겨보세요!' rows='4' />
    </div>
  </div>
</template>

<script>
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'

export default {
  name: 'IntroduceContainer',
  components: { ProfileTitle }
}
</script>

<style lang='scss' scoped>
.introduce-container {
  display: flex;
  flex-direction: column;


}

.introduce-textarea {
  background: $grey-1;
  margin-top: 3.2vh;
  font-size: $kor-20;

  textarea {
    background: $grey-1;
    width: 90%;
    margin-top: 1.1vh;
    margin-left: 0.9vw;
    resize: none;

  }

  textarea::placeholder {
    color: $grey-4;
    font-weight: 500;
    font-size: $kor-20;
    position: absolute;
  }

  textarea:focus {
    outline: none;
  }
}
</style>
