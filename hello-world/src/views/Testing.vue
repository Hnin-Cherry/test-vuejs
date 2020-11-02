<template>
  <div>
    <TestingOne />
    <h2>This is H2 Tag.</h2>
    <p>This is Vue paragraph2.</p>
    <p>{{testTitle}}</p>
    <p v-bind:title="hovermsg">This is an hover message.I am appreciate with this.</p>
  </div>
</template>
<script>
import TestingOne from "@/components/TestingOne.vue";
export default {
  name: "Testing",
  components: {
    TestingOne
  },
  data() {
      return {
          testTitle: "Hello Everyone",
          hovermsg: "You loaded this page on " + new Date().toLocaleString()
      }
  }
};
</script>
<style scoped>
</style>