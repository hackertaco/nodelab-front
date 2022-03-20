<template>
  <div class='main-container'>
    <img
      alt='main-img' class='main-img' src='@/assets/img/main.png' />
    <div class='lists-container contents'>
      <study-list-container v-for='(title, i) in titleObject' :key='i' :title='title'></study-list-container>
    </div>
    <footer-container></footer-container>
  </div>
</template>

<script>
import StudyListContainer from '~/components/main/StudyListContainer'
import FooterContainer from '~/components/parts/Footer'

export default {
  name: 'IndexComponent',
  components: { StudyListContainer, FooterContainer },
  setup() {
    const titleObject = [
      {
        main: '곧 시작하는 스터디',
        sub: '빠르게 스터디에 합류해 성장을 시작해보세요'
      },
      {
        main: '최근 개설된 스터디',
        sub: '만들어진 스터디와 함께해보세요.'
      }
    ]
    return {
      titleObject
    }
  }
}
</script>

<style scoped>
.main-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.main-img {
  width: 67.7%;
  position: relative;
  left: 16.5%;
  overflow: hidden;
}

.lists-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 25vh;
}
</style>
