<template>
  <span class="todoItem">
    <div class="todoDetail">
      <input class="checkbox" v-if="todo.completed == true" checked type="checkbox" @click="mark">
      <input class="checkbox" v-else-if="todo.completed == false" type="checkbox" @click="mark">
      <div>{{ todo.title }}</div>
    </div>
    <div class="todoDel">
      <button class="item-del" @click="$emit('del-todo', todo.id)">x</button>
    </div>
  </span>

</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    mark() {
      this.$emit('compTodo', this.todo.id)
    }
  }
};

</script>

<style scoped>
.todoDetail {
  display: flex;
}



.item-del {
  background-color: red;
  font-size: 12px;
  color: whitesmoke;
  border-radius: 15px;
  border: none;
  width: 30px;
  float: right;
  height: 30px;
  font-size: 18px;
  font-weight: bold;
}

.todoItem {
  display: flex;
  background-color: rgb(213, 223, 75);
  border-radius: 10px;
  font-size: 18px;
  margin: 5px;
  padding: 8px;
  margin-left: 10px;
  margin-right: 10px;
  align-items: center;
  justify-content: space-between;
}

.checkbox {
  margin-left: 10px;
  margin-right: 10px;
  transform: scale(1.5);
}
</style>
