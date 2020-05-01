<template>
  <div>
    <h3 class="text-primary">Tracery</h3>
    <p class="text-info">{{ story }}</p>
  </div>
</template>

<script>
import traceryGrammar from "tracery-grammar";

const grammar = traceryGrammar.createGrammar({
  animal: ["panda", "fox", "capybara"],
  emotion: ["sad", "happy", "happy", "angry"],
  origin: ["I am #emotion.a# #animal#"],
});

grammar.addModifiers(traceryGrammar.baseEngModifiers);

export default {
  name: "tracery",
  data() {
    return {
      stories: [],
      story: null,
    };
  },
  mounted() {
    this.story = grammar.flatten("#origin#");
  },
};
</script>
