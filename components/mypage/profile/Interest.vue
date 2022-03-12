<template>
  <div class='interest-container'>
    <profile-title>
      <template #title>관심사</template>
    </profile-title>
    <select-list class='interest-margin'></select-list>
  </div>
</template>

<script>
import ProfileTitle from '~/components/mypage/profile/ProfileTitle'
import SelectList from '~/components/mypage/profile/SelectList'

export default {
  name: 'InterestContainer',
  components: { SelectList, ProfileTitle }
}
</script>

<style lang='scss' scoped>
.interest-container {
  display: flex;
  flex-direction: column;
}

.interest-margin {
  margin-top: 1.2vh;
}
</style>
