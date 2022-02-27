<template>
  <div class='footer-container'>
    <div class='tag-container'>
      <span>#태그태그</span>
      <span>#태그내용입니다</span>
      <span>#태그내용</span>
    </div>
    <div class='button-container'>
      <div class='icon-container'>
        <icon-comment></icon-comment>
        <span>5</span>
      </div>
      <div class='icon-container'>
        <icon-like></icon-like>
        <span>5</span>
      </div>
      <icon-bookmark></icon-bookmark>
    </div>
  </div>
</template>

<script>
import IconComment from 'assets/svg/IconComment'
import IconLike from 'assets/svg/IconLike'
import IconBookmark from 'assets/svg/IconBookmark'

export default {
  name: 'StudyItemFooter',
  components: { IconBookmark, IconLike, IconComment }
}
</script>

<style lang='scss' scoped>
.footer-container {
  display: flex;
  justify-content: space-between;
  margin-top: 24px;
  width: 100%;
}

.tag-container {
  color: $grey-4;
  font-size: 0.3vw;
  width: 70%;

  span {
    margin-right: 2%;
  }
}

.button-container {
  color: $dark-191919;
  width: 25%;
  display: flex;
  font-weight: 500;
  font-family: Chakra Petch;
  line-height: 29px;
  align-items: center;
  position: relative;
  bottom: 5px;

}

.button-icon {
  width: 10px;
  height: 10px;
  background-color: #191919;

}

.icon-container {
  width: 40%;
  display: flex;
  align-items: center;


  span {
    margin-left: 8%;
    margin-right: 12%;
  }
}
</style>
