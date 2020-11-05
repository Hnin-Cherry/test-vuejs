<template>
  <div>
      <h2>Class Binding(Array Syntax)</h2>
      <div :class="[activeClass,errorClass]">This is Array Syntax Testing.</div>
      <div :class="[condition ? activeClass : '',errorClass]">This is Ternary array Syntax</div>
  </div>
</template>

<script>
    export default {
        name: "ArraySyntax",
        data() {
            return {
                activeClass: 'now',
                errorClass: 'error',
                condition : true
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .now {
        color: green;
    }
    .error {
        background-color: black;
        margin: 10px;
    }
</style>
