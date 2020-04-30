<template>
  <div id="app" class="container">
    <HelloWorld msg="Message" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>
