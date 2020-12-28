<template>
  <div class="iterative-counter">
    <ul>
      <li>
        <input id="angular" type="checkbox" />
        <label for="angular">Angular</label>
      </li>
      <li>
        <input id="react" type="checkbox" />
        <label for="react">React</label>
      </li>
      <li>
        <input id="vue" type="checkbox" />
        <label for="vue">Vue</label>
      </li>
    </ul>
    <p class="count" data-unit="个">框架：</p>
    <p class="weight" data-unit="%">权重：</p>

    <div class="clampBox"></div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.iterative-counter {
  /* clamp() 函数的作用是把一个值限制在一个上限和下限之间，当这个值超过最小值和最大值的范围时，在最小值和最大值之间选择一个值使用。 
  当首选值比最小值要小时，则使用最小值。
  当首选值介于最小值和最大值之间时，用首选值。
  当首选值比最大值要大时，则使用最大值。
  */
  .clampBox {
    width: clamp(100px, 100%, 200px);
    height: 100px;
    background: red;
  }
  ul {
    counter-reset: index 0 count 0 weight 0;
  }
  li {
    display: flex;
    position: relative;
    align-items: center;
    counter-increment: index 1;
    &::before {
      content: counter(index) '、';
    }
    & + li {
      margin-top: 10px;
    }
  }
  input {
    overflow: hidden;
    position: absolute;
    width: 0;
    height: 0;
    opacity: 0;
    &:checked + label::before {
      color: #3c9;
      content: '\2713';
    }
  }
  label {
    display: flex;
    align-items: center;
    height: 20px;
    &::before {
      margin-right: 5px;
      border: 1px solid #3c9;
      width: 20px;
      height: 20px;
      cursor: pointer;
      line-height: 20px;
      text-align: center;
      color: transparent;
      content: '';
      transition: all 300ms;
    }
  }
  p {
    margin-top: 10px;
    &.count::after {
      content: counter(count) attr(data-unit);
    }
    &.weight::after {
      content: counter(weight) attr(data-unit);
    }
  }
  #angular:checked {
    counter-increment: count 1 weight 20;
  }
  #react:checked {
    counter-increment: count 1 weight 50;
  }
  #vue:checked {
    counter-increment: count 1 weight 30;
  }
}
</style>