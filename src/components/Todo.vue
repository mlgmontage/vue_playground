<template>
  <div>
    <h3>Todo App</h3>
    <form @submit="addTodo">
      <input type="text" v-model="text" />
      <input type="submit" value="Add" />
    </form>
    <ul>
      <li v-for="(todo, inx) in filterTodos()" :key="inx">
        <span :class="todo.completed ? 'completed' : ''">
          <input type="checkbox" v-model="todo.completed" />
          <span>{{todo.text}}</span>
        </span>
      </li>
    </ul>
    <div>
      <label>
        <input type="radio" name="mode" value="all" v-model="mode" />all
      </label>
      <label>
        <input type="radio" name="mode" value="completed" v-model="mode" />completed
      </label>
      <label>
        <input type="radio" name="mode" value="icebox" v-model="mode" />icebox
      </label>
      <br />
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoApp",
  data() {
    return {
      text: "",
      mode: "all",
      todos: [
        { text: "washing dishes", completed: false },
        { text: "jogging", completed: true },
        { text: "clean the code", completed: false }
      ]
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      this.todos.unshift({ text: this.text, completed: false });
      this.text = "";
    },
    filterTodos() {
      if (this.mode === "all") {
        return this.todos;
      }
      if (this.mode === "completed") {
        return this.todos.filter(todo => todo.completed === true);
      }
      if (this.mode === "icebox") {
        return this.todos.filter(todo => todo.completed === false);
      }
    }
  }
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}

.hidden {
  display: none;
}
</style>