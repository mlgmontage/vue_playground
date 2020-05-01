<template>
  <div>
    <h3 class="text-primary">Tracery</h3>
    <button class="btn btn-info" @click="newStory">new story</button>
    <b-list-group>
      <b-list-group-item
        variant="success"
        v-for="(story, inx) in stories"
        :key="inx"
      >
        {{ story }}
      </b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
import traceryGrammar from "tracery-grammar";

const animal = ["panda", "fox", "capybara"];
const emotion = ["sad", "happy", "happy", "angry"];
const origin = ["I am #emotion.a# #animal#"];

const grammar = traceryGrammar.createGrammar({
  animal,
  emotion,
  origin,
});

grammar.addModifiers(traceryGrammar.baseEngModifiers);

export default {
  name: "tracery",
  data() {
    return {
      stories: [],
    };
  },
  methods: {
    newStory() {
      this.stories.push(grammar.flatten("#origin#"));
    },
  },
  mounted() {
    this.stories.push(grammar.flatten("#origin#"));
  },
};
</script>
