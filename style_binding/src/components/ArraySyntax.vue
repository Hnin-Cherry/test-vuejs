<template>
  <div>
    <div :style="[baseStyle, overrideStyle]">Style Binding(Array Syntax)</div>
  </div>
</template>

<script>
export default {
  name: 'ArraySyntax',
  data() {
    return {
      baseStyle: {
        border: '2px solid red'
      },
      overrideStyle: {
        color: 'blue',
        'text-shadow': '2px 2px 4px blue'
      }
    }
  }
}
</script>

<style scoped>

</style>
