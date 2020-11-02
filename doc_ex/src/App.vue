<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Hello World" />
    <!--<ol>
      <HelloWorld v-for="flower in arr_flowers" v-bind:key="flower.id" v-bind:flowers="flower"/>
    </ol>-->
  </div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      arr_flowers: [
        { id: 0, text: "Rose" },
        { id: 1, text: "Jasmine" },
        { id: 2, text: "Sunflower" },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
