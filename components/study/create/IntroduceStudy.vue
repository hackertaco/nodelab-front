<template>
  <div class='introduce_container'>
    <div class='introduce_title_box'>
      <input placeholder='8주만에 알고리즘 완전 뽀개기' />
    </div>
    <div class='introduce_text_box'>
      <textarea />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IntroduceStudy'
}
</script>

<style lang='scss' scoped>
.introduce_container {
  width: 100%;
  color: $grey-4;
  background: #FFFFFF;
  border: 1px solid $grey-3;
  box-sizing: border-box;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
}

.introduce_title_box {
  height: 20.7%;
  width: 100%;
  border-bottom: 1px solid $grey-3;
  display: flex;
  justify-content: center;
  align-items: center;
}

.introduce_title_box input {
  outline: none;
  width: 93%;
  height: 45%;
  font-weight: 700;
  font-size: $kor-20;
  line-height: 1.35;

  /* grey 4_#8D8D8D */

  color: $grey-4;
}


.introduce_text_box {
  height: 79.2%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.introduce_text_box textarea {
  width: 93%;
  height: 85.8%;
  outline: none;
  resize: none;
  font-weight: 500;
  font-size: $kor-20;
  line-height: 1.35;

  /* grey 4_#8D8D8D */

  color: $grey-4;

}
</style>
