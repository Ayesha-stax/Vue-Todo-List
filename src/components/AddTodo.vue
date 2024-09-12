<template>
    <form>
        <input class="addTodoInput" placeholder="Add a new item" v-model="title" />
        <button class="submitBtn" @click="addTodo">Submit</button>
    </form>
</template>


<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: ""
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault()
            const todo = {
                title: this.title,
                completed: false
            }
            this.$emit("addTodo", todo)
            this.title = ""
        }
    }
}
</script>

<style>
.addTodoInput {
    margin: 10px;
    width: 75%;
    height: 40px;
    border-radius: 10px;
    border: none;
    background-color: bisque;
    padding: 2px;
    padding-left: 8px;
    font-size: 18px;

}

.submitBtn {
    width: 20%;
    height: 44px;
    background-color: rgb(75, 75, 215);
    border: none;
    border-radius: 10px;
    font-size: 18px;
    color: antiquewhite
}
</style>