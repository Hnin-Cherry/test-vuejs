<template>
  <div>
    <div :style="{color: activeColor, fontSize: fontSize + 'px'}">Style Binding</div>
    <p :style="styleObject">Style Object</p>
    <ArraySyntax/>
  </div>
</template>

<script>
import ArraySyntax from './components/ArraySyntax.vue'

export default {
  name: 'App',
  components: {
    ArraySyntax,
  },
  data() {
    return {
      activeColor: 'red',
      fontSize: 20,
      styleObject: {
        color: 'white',
        fontSize: '30px',
        'background-color': 'black'
      }
    }
  }
 
}
</script>

<style>

</style>
