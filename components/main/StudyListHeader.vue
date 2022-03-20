<template>
  <div class='list-header-container'>
    <icon-down class='icon' width='4%'></icon-down>
    <div class='header-container'>
      <div class='header-title'>
        <div class='title'>{{ title.main }}
        </div>
        <div class='rectangular'></div>
      </div>
      <span class='description'>{{ title.sub }}</span>
    </div>
  </div>
</template>

<script>
import IconDown from 'assets/svg/IconDown'

export default {
  name: 'StudyListHeader',
  components: { IconDown },
  props: {
    title: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

<style lang='scss' scoped>
.list-header-container {
  width: 100%;
  display: flex;
  margin-bottom: 2vh;
}

.rectangular {
  width: 8px;
  height: 8px;
  background-color: $dark-191919;
  margin-top: 7px;
  margin-left: 1%;
}

.title {
  font-size: 1.875vw;
  color: $dark-191919;
  font-weight: bold;
  line-height: 1.5;
}

.header-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.icon {
  margin-right: 3%;
  text-align: center;
  margin-left: 1%;
  margin-top: 0.5%;
}

.header-title {
  display: flex;
  align-items: start;
}

.description {
  color: $grey-4;
  font-size: $eng-30;
  font-weight: 400;
  //line-height: 41px;

}
</style>
