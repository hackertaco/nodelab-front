<template>
  <div class='list-container'>
    <div v-for='(l, index) in list' :key='index' class='list-item'>
      {{ l.toUpperCase() }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'SelectList',
  setup() {
    const list = ['frontend', 'backend', 'fullstack', 'devops', 'manager', 'mobile', 'ai', 'data', 'database']
    return {
      list
    }
  }
}
</script>

<style lang='scss' scoped>
.list-container {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  color: $grey-3;
  font-weight: 500;
  font-family: "Chakra Petch", sans-serif;
  font-size: $kor-20;
}

.list-item {
  margin-right: 1.25vw;
  margin-top: 2vh;
}
</style>
