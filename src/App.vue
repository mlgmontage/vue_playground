<template>
  <div id="app" class="container">
    <HelloWorld msg="Message" />
    <Quiz />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Quiz from "./components/Quiz.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Quiz,
  },
};
</script>
