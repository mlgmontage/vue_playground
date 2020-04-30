<template>
  <div>
    <h3>Todo App</h3>
    <form @submit="addTodo">
      <input type="text" v-model="text" />
      <input type="submit" value="Add" />
    </form>
    <ul>
      <li v-for="(todo, inx) in todos" :key="inx">
        <span :class="todo.completed ? 'completed' : ''">
          <input type="checkbox" v-model="todo.completed" />
          {{todo.text}}
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoApp",
  data() {
    return {
      text: "",
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
    }
  }
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>