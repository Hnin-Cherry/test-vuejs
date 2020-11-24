<template>
  <div class="myDiv">
    <h1 v-if="awesome">Vue is Awesome!</h1>
    <h1 v-else>Oh No!</h1>

    <h2 v-if="Math.random() > 5">Now You can see Me</h2>
    <h2 v-else>Now You Don't</h2>

    <h3 v-if="type === 'A'">A</h3>
    <h3 v-else-if="type === 'B'">B</h3>
    <h3 v-else-if="type === 'C'">C</h3>
    <h3 v-else>Not A/B/C</h3>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      awesome: true,
      type: 'C'
    }
  }
}
</script>

<style>
 h1 {
   color:rebeccapurple;
 }
 .myDiv {
   animation: mymove 5s infinite;
 }
 @keyframes mymove {
   50% {text-shadow: 10px 10px 30px blue;}
 }
</style>
