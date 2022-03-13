<template>
  <div class='contents setting-container'>
    <div class='setting-items'>
      <alarm-setting></alarm-setting>
      <receive-setting></receive-setting>
    </div>
    <other-things></other-things>
  </div>
</template>

<script>
import AlarmSetting from '~/components/mypage/setting/AlarmSetting'
import ReceiveSetting from '~/components/mypage/setting/ReceiveSetting'
import OtherThings from '~/components/mypage/setting/OtherThings'

export default {
  name: 'SettingContainer',
  components: { OtherThings, ReceiveSetting, AlarmSetting }
}
</script>

<style scoped>
.setting-container {
  display: flex;
  justify-content: center;
}

.setting-items {
  display: flex;
  flex-direction: column;
  width: 30.4vw;

}
</style>
