<template>
  <div class='main-container'>
    <img
      alt='main-img' class='main-img' src='@/assets/img/main.png' />
    <div class='lists-container'>
      <study-list-container></study-list-container>
      <study-list-container></study-list-container>
    </div>
    <footer-container></footer-container>
  </div>
</template>

<script>
import StudyListContainer from '~/components/main/StudyListContainer'
import FooterContainer from '~/components/parts/Footer'

export default {
  name: 'IndexComponent',
  components: { StudyListContainer, FooterContainer }
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
  width: 62.5%;
  display: flex;
  flex-direction: column;
  margin-bottom: 25vh;
}
</style>
