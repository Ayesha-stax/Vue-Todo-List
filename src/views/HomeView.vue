<template>
  <div class="todo-app">
    <TodoList v-bind:todos="todos" v-on:del-todo="deleteTodo" v-on:markComplete="markComplete" v-on:addTodo="addTodo" />
  </div>
</template>

<script>
import TodoList from "../components/todo-list";
import axios from "axios"
export default {
  name: "HomePage",
  components: {
    TodoList,
  },
  data() {
    return {
      todos: [],
    };
  },
  created() {
    axios.get("https://jsonplaceholder.typicode.com/todos").then((res) => this.todos = res.data).catch((ex) => console.log(ex));

  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`).then(() => this.todos = this.todos.filter((todo) => todo.id !== id)).catch((ex) => console.log(ex))
    },
    markComplete(id) {
      const index = this.todos.findIndex((todo) => todo.id === id)
      this.todos[index].completed = !this.todos[index].completed
    },
    addTodo(todo) {
      const { completed, title } = todo
      axios.post("https://jsonplaceholder.typicode.com/todos", { completed, title }).then((res) => this.todos = [...this.todos, res.data]).catch((ex) => console.log(ex))
    }
  }
};
</script>

<style>
.todo-app {
  height: 100%;
  width: 100%;
  justify-content: center;
  align-items: center;
}

html {
  height: 100vh;
  width: 100%;
  background-color: grey;
  display: flex;
  justify-content: center;
  align-items: center;
}

#app {
  height: 100%;
  width: 100%;
  background-color: rgb(88, 248, 101);
  border-radius: 20px;
}

body {
  height: 80vh;
  width: 40%;
}
</style>
