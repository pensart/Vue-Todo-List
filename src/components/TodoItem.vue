<template>
    <p class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <input type="checkbox" v-on:change="markComplete">
        {{todo.title}}
        <button class="del" @click="$emit('del-todo', todo.id)" >X</button>
    </p>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #F4F4F4;
        padding: 10px;
        border-bottom: 1px #CCC dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #FF0000;
        color: #FFF;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>