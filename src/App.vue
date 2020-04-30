<template>
  <div class="container" id="app">
    <HelloWorld msg="Message" />
    <Todo />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Todo from "./components/Todo.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Todo,
  },
};
</script>
