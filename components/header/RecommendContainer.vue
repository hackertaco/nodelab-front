<template>
  <div class='recommend-contents'>
    <div class='recommend-title'>
      <icon-star></icon-star>
      <span>추천 카테고리</span>
      <div class='rectangular'></div>
    </div>
    <divider-line class='divider' color='grey'></divider-line>
    <div class='recommend-category'>
      <div class='item'>
        <div class='btn'>카테고리</div>
        <div class='line'>
        </div>
      </div>
      <div class='item'>
        <div class='btn'>카테고리</div>
        <div class='line'></div>
      </div>
      <div class='item'>
        <div class='btn'>카테고리</div>
        <div class='line'></div>
      </div>
      <div class='item'>
        <div class='btn'>카테고리</div>
        <div class='line'></div>
      </div>
    </div>
  </div>
</template>

<script>
import IconStar from 'assets/svg/IconStar'
import DividerLine from '~/components/parts/Divider'

export default {
  name: 'RecommendContainer',
  components: { DividerLine, IconStar }
}
</script>

<style lang='scss' scoped>
.recommend-contents {
  width: 62.5%;
  display: flex;
  flex-direction: column;

  .divider {
    margin-bottom: 6vh;
  }

  .recommend-category {
    display: flex;

    .item {
      display: flex;
      flex-direction: column;
      margin-right: 1.25vw;
      align-content: center;
      cursor: pointer;

      .btn {
        background-color: $grey-1;
        width: 6vw;
        height: 4vh;
        margin-bottom: 5px;
        font-size: $kor-20;
        color: $grey-4;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      .line {
        border-bottom: 1px solid #E5E5E5;
      }
    }

    .item:hover {

      .btn {
        color: $pink;
        font-weight: bold;
        margin-bottom: 0;
      }

      .line {
        border-bottom: 1px solid $pink;
      }
    }
  }

  .recommend-title {
    display: flex;
    align-items: center;
    position: relative;
    top: 4vh;
    margin-bottom: 6vh;

    span {
      margin-left: 0.9vw;
      font-size: $kor-36;
      line-height: 49px;
      font-weight: bold;
    }

    .rectangular {
      width: 8px;
      height: 8px;
      background-color: $dark-191919;
      margin-top: 7px;
      margin-left: 0.2vw;
      position: relative;
      bottom: 25%;
    }
  }

}
</style>
