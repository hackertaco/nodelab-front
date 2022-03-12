<template>
  <div class='position-container'>
    <profile-title>
      <template #title>현재 포지션</template>
    </profile-title>
    <select-list class='position-margin'></select-list>
  </div>
</template>

<script>
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'
import SelectList from '~/components/mypage/profile/SelectList'

export default {
  name: 'PositionContainer',
  components: { SelectList, ProfileTitle }
}
</script>

<style scoped>
.position-container {
  display: flex;
  flex-direction: column;
}

.position-margin {
  margin-top: 1.2vh;

}
</style>
