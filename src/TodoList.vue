<script setup>
import { ref } from 'vue'

let id = 0
const newTodo = ref('')
const todos = ref([
    {id: id++, text: 'Ngocok'},
    {id: id++, text: 'Ngoding'},
    {id: id++, text: 'Ngehalu'}
])

function addTodo(){
    todos.value.push({ id: id++, text: newTodo.value })
}

function removeTodo(todo){
    todos.value = todos.value.filter((hapus)=> hapus !== todo );
}

</script>

<template>
<h1>kegiatan hari ini todo list aneh-aneh</h1>
    <form @submit.prevent="addTodo">
        <input type="text" name="" id="" v-model="newTodo">
        <button>Add Todo</button>
    </form>
    <ul>
        <li v-for="todo in todos" :key="todo.id">
            {{ todo.text }}
            <button @click="removeTodo(todo)">x</button>
        </li>
    </ul>
</template>

<style scoped>

</style>