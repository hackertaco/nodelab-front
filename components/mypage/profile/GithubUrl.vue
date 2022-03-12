<template>
  <div class='git-container'>
    <profile-title>
      <template #title>Github URL</template>
    </profile-title>
    <div class='git-input'>
      <input placeholder='이메일을 입력해주세요' />
    </div>
  </div>
</template>

<script>
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'

export default {
  name: 'GithubUrl',
  components: { ProfileTitle }
}
</script>

<style lang='scss' scoped>
.git-container {
  display: flex;
  flex-direction: column;

  input {
    background: $grey-1;
    margin-top: 1.1vh;
    margin-left: 0.9vw;
    width: 80%;
    font-size: $kor-20;
  }

  input::placeholder {
    color: $grey-4;
    font-weight: 500;
    font-size: $kor-20;
    position: absolute;
  }

  input:focus {
    outline: none;
  }


  #searchFieldText:focus {
    margin-top: 1.1vh;
    margin-left: 0.9vw;
    position: absolute;

  }

}

.git-input {
  margin-top: 3.2vh;
  background: $grey-1;
  height: 5.9vh;
  position: relative;
  font-size: $kor-20;
}
</style>
