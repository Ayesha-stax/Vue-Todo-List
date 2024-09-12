<template>
  <div class="todo-list">

    <AddTodo v-on:addTodo="addTodo" />
    <div class="list">

      <TodoItem v-on:del-todo="$emit('del-todo', todo.id)" v-on:compTodo="mark" v-for="todo in todos"
        v-bind:key="todo.id" v-bind:todo="todo" />
    </div>
  </div>
</template>


<script>
import TodoItem from "./todo-item"
import AddTodo from "./AddTodo"

export default {
  name: "TodoList",
  props: ["todos"],
  components: { TodoItem, AddTodo },
  methods: {
    mark(id) {
      this.$emit('markComplete', id)
    },
    addTodo(todo) {
      console.log(todo, "list")
      this.$emit("addTodo", todo)
    }
  }


};
</script>

<style scoped>
::-webkit-scrollbar {
  width: 10px;

}

/* Track */
::-webkit-scrollbar-track {
  background: rgb(88, 248, 101);
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #888;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}


.list {
  overflow-y: scroll;
}


.todo-list {
  width: 100%;
  height: 100%;
  background-color: rgb(88, 248, 101);
  display: flex;
  flex-direction: column;
  border-radius: 20px;

}
</style>
