<template>
  <div>
    <h2>Component</h2>
    <form @submit="add">
      <input type="text" name="todo" v-model="todo" />
    </form>
    <ol>
      <li v-for="(todo, index) in todos" :key="index">{{ todo | kittyfy }}</li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      todos: ["kitkat", "bison", "hikki"],
      todo: ""
    };
  },
  methods: {
    add(e) {
      // messy method
      e.preventDefault();
      this.todos.push(this.todo);
      this.todo = "";
    }
  },
  filters: {
    kittyfy(el) {
      return el + "fy";
    }
  }
};
</script>