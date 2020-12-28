<template>
  <div>
    <button id="red-theme-btn">11</button>
    <button id="blue-theme-btn">22</button>
    <button id="green-theme-btn">33</button>
  </div>
</template>

<script>
export default {
  data() {},
  methods: {
    changeAllBtnStyle() {
      // 变换颜色主题的一种解决方案，好处在于只需维护一套CSS代码切换控件会使用纯CSS实现暗黑模式换肤。
      ;['red', 'blue', 'green'].forEach(v => {
        const btn = document.getElementById(`${v}-theme-btn`)
        btn.addEventListener('click', () => document.body.style.setProperty('--bg-color', v))
      })
    }
  }
}
</script>

<style lang="scss" scoped>
:root {
  --bg--color: red;
}
.title {
  background-color: var(--bg--color);
}
.desc {
  background-color: var(--bg--color);
}
</style>