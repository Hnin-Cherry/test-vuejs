<template>
  <div>
    <!--<li>{{flowers.text}}</li>-->
    <p>{{ msg }}</p>
    <p>{{ name }}</p>
    <p>{{ message }}</p>
    <p v-bind:title="hovermsg">
      This is an hover message.I appreciate with this.
    </p>
    <p v-if="seen">You can see me.</p>
    <ol>
      <li v-for="todo in todos" v-bind:key="todo.text">{{ todo.text }}</li>
    </ol>
    <button @click="addList">Add New List</button>
    <button @click="deleteList">Delete List</button><br />
    <button v-on:click="reverseMessage">Reverse Message</button>
    <h2>{{ inputmsg }}</h2>
    <input v-model="inputmsg" /><br />
    <button v-bind:disabled="isButtonDisabled">DisabledButton</button><br />
    <h3>The number is : {{ number + 1 }}</h3>
    <p>{{ num == 22 ? "Yes, Num is 22" : "Any Num" }}</p>
    <a v-bind:[attributeName]="'https://vuejs.org/v2/guide/syntax.html'"
      >This is a tag.</a
    ><br />
    <p>{{ showmsg }}</p>
    <button v-on:[eventName]="showMsg">DynamicEvent</button><br />
    <p>Hello {{ getTitle }}</p>

    <!--modifier-->
    <form v-on:submit.prevent="onSubmit">
      <h3>{{ fullName }}</h3>
      FirstName <input type="text" v-model="first" /><br />
      SecondName<input type="text" v-model="second" /><br />
      <button type="submit" id="btnSubmit">Submit</button>
    </form>

    <p>Count is {{ count}}</p>
    
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    flowers: [],
  },
  data() {
    return {
      name: "Vue Js",
      hovermsg: "You loaded this page on " + new Date().toLocaleString(),
      seen: true,
      todos: [{ text: "Apple" }, { text: "Orange" }, { text: "Grape" }],
      message: "I am Hnin Cherry.",
      inputmsg: "You are an apple of my eye",
      a: 1,
      isButtonDisabled: true,
      number: 21,
      num: 22,
      attributeName: "href",
      eventName: "click",
      showmsg: "",
      title: "Vue",
      fullName: "",
      first: "",
      second: "",
      count: 4
    };
  },
  methods: {
    addList: function () {
      this.todos.push({ text: "Pineapple" });
    },
    deleteList: function () {
      this.todos.pop();
    },
    reverseMessage: function () {
      this.message = this.message.split(" ").reverse().join(" ");
    },
    showMsg: function () {
      this.showmsg = "This is Dynamic Event";
    },
    onSubmit: function () {
      this.fullName = "Hello " + this.first + " " + this.second;
    },
    increment: function () {
      var self = this;
      var interval = setInterval(function () {
        self.count++;
        if(self.count == 20) {
          clearInterval(interval);
        }
      }, 1000);
      
    }
  },

  computed: {
    getTitle() {
      return this.title;
    }

  },

  created() {
    alert("a is " + this.a);
    this.increment();
  },
};
</script>
<style scoped>
button {
  color: white;
  background-color: violet;
}
</style>