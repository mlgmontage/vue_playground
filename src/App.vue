<template>
  <div id="app" class="container">
    <HelloWorld msg="Message" />
    <tracery />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import tracery from "./components/tracery.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    tracery,
  },
};
</script>
