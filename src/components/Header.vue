<template>
    <h1 class="todo-heading">TODOs</h1>
    <nav class="navigation">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
    </nav>
</template>

<script>
export default {
    name: "HeaderComp"
}
</script>

<style>
.navigation {
    margin-top: 5px;
    margin-bottom: 10px;
    padding: 0px;
}

.todo-heading {
    align-self: center;
    font-size: 50px;
    color: purple;
    margin-bottom: 0px;
    margin-top: 10px
}
</style>