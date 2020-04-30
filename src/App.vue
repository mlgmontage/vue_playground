<template>
  <div id="app">
    <HelloWorld msg="Message" />
    <Forms />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Forms from "./components/Form.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Forms
  }
};
</script>

