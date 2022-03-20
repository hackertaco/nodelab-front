<template>
  <div class='body-container'>
    <thum-nail :style-object='thumbnail' :title='title'></thum-nail>
    <div class='body-content-container'>
      <div class='body-header-container'>
        <span class='category'>알고리즘</span>
        <div>
          <span class='d-day'>D-4</span>
          <span class='kind'>스터디</span>
        </div>
      </div>
      <div class='body-title'>타이틀 노출 위치 타이틀 노출 위치 타이틀 노출 위치</div>
      <div class='body-info'>
        <div class='info-item'>정원 6명</div>
        <div class='info-item'>신청 6명</div>
        <div>시작 예정일 12.02</div>
      </div>
    </div>
  </div>
</template>

<script>
import ThumNail from '~/components/parts/ThumbNail'

export default {
  name: 'StudyItemBody',
  components: { ThumNail },
  props: {
    title: {
      type: String
    }
  },
  setup() {
    const thumbnail = {
      width: '35%',
      height: '100%',
      background: '#F2F2F2'
    }
    return { thumbnail }
  }
}
</script>

<style lang='scss' scoped>
.body-container {
  font-family: 'Noto Sans';
  width: 100%;
  height: 138px;
  display: flex;
  justify-content: space-between;
  margin-bottom: 24px;
}

.body-content-container {
  display: flex;
  flex-direction: column;
  width: 70%;
  margin-left: 5%;
  position: relative;
}

.body-header-container {
  width: 100%;
  display: flex;
  justify-content: space-between;
  //font-size: $kor-p4;
  font-size: 0.3vw;
}

.category {
  color: $grey-4;
  //font-size: $kor-p4;
  font-size: 0.3vw;
}

.d-day {
  color: $dark-191919;
  margin-right: 8px;
}

.kind {
  color: #46DA00;
}

.body-title {
  color: $dark-191919;
  margin-top: 5px;
  font-weight: 600;
  //font-size: 1.2rem;
  font-size: 1.2vw;
  line-height: 33px;
  word-wrap: break-word;
  text-overflow: ellipsis;
  display: -webkit-box;
  overflow: hidden;
  -webkit-line-clamp: 2; /* 라인수 */
  -webkit-box-orient: vertical;
  line-height: 1.2;
}

.body-info {
  color: $grey-4;
  //font-size: 0.875rem;
  font-size: 0.3vw;
  font-family: Chakra Petch !important;
  display: flex;
  position: absolute;
  bottom: 0;
}

.info-item {
  margin-right: 6px;
}
</style>
