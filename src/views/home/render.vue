<template>
  <div :id="id" class="wrapper" :class="{'foo': true, 'bar': false}" :style="{color: 'red', fontSize: '18px'}" v-bind="$attrs" v-on="$listeners" @click="(e) => console.log(e)"> hello world! </div>
</template>
<script>
export default {
  name: 'custom-element',
  data(){
    return {
      id: 'id-demo'
    }
  }
}
</script>

<style>
.wrapper{
  display: block;
  width: 100%;
}
</style>