<template>
  <div>
    <ul class="strip-loading">
      <li v-for="v in 6" :key="v"></li>
    </ul>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.strip-loading {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 200px;
  li {
    border-radius: 3px;
    width: 6px;
    height: 30px;
    background-color: #f66;
  }
}
</style>