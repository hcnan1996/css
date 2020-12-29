<script>
import Vue from 'vue'
Vue.component('custom-element', {
  render(createElement) {
    var self = this
    return createElement('div', {
      class: {
        foo: true,
        bar: false
      },
      style: {
        border: '1px solid',
        padding: '10px'
      }
    })
  }
})
</script>