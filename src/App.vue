<template>
  <div id="app">
    <HelloWorld msg="Message" />
    <List />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import List from "./components/List.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    List
  }
};
</script>

