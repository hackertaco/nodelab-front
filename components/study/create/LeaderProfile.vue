<template>
  <div class='profile_container'>
    <div class='profile_box'>
      <div class='profile_title_container'>
        <div class='profile_icon'>
          <icon-profile-heart></icon-profile-heart>
        </div>
        <div class='profile_title_box'>
          <div class='profile_title_nickname'>팀장 닉네임</div>
          <div class='profile_title_main_keyword'>대표 키워드</div>
        </div>
      </div>
      <div class='profile_memo_container'>
        <div class='profile_memo_square'></div>
        <input placeholder='팀장의 메모 기입란' />
      </div>
      <div class='acc-info'>
        <div class='acc-info-ratio-title'>성취율</div>
        <div class='acc-info-ratio'>80%</div>
      </div>
      <div class='acc-ratio'>
        <div class='acc-ratio-real'></div>
      </div>
    </div>
  </div>
</template>

<script>
import IconProfileHeart from 'assets/svg/IconProfileHeart'

export default {
  name: 'LeaderProfile',
  components: { IconProfileHeart }
}
</script>

<style lang='scss' scoped>
.profile_container {
  //width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid $grey-3;
  background-color: #fff;
}

.profile_box {
  width: 85%;
  height: 80%;
  display: flex;
  flex-direction: column;

}

.profile_title_container {
  display: flex;
  width: 100%;
  height: 30%;
  align-items: center;
}

.profile_icon {
  width: 30%;
}

.profile_title_box {
  display: flex;
  flex-direction: column;

}

.profile_title_nickname {
  font-weight: 600;
  font-size: $eng-24;
  line-height: 1.3;
}

.profile_title_main_keyword {
  font-weight: 700;
  font-size: $kor-20;
  line-height: 2;


  color: $grey-4;
}

.profile_memo_container {
  width: 100%;
  height: 17.5%;
  background: $grey-2;
  border-radius: 4px;
  position: relative;
  display: flex;
  align-items: center;
  margin-top: 6px;
}

.profile_memo_square {
  width: 6px;
  margin-left: 8px;
  margin-right: 4px;
  height: 6px;
  background: $dark-191919;

}

.profile_memo_container input {
  border: none;
  background-color: $grey-2;
  color: #191919;
  height: 80%;
  width: 90%;
  outline: none;
}

.acc-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 15.7%;

  &-ratio {
    font-size: $eng-24;
    font-weight: 600;
    font-family: "Chakra Petch", sans-serif;

    &-title {
      font-size: $kor-14;
      color: $grey-4;
      font-weight: bold;

    }
  }
}

.acc-ratio {
  position: relative;
  background: $grey-1;
  width: 100%;
  height: 2.1%;
  border-radius: 4px;
  margin-top: 1.3vh;

  &-real {
    height: 2.2vh;
    border-radius: 4px;
    position: relative;
    background: $mint;
    width: 80%;
  }
}
</style>
