<script setup>
import { ref } from 'vue'; 
const todo = ref('');

function clear() { // mnghapus data formnya ketika data todonya berhasil di tambahkan
    todo.value = "";
    }
</script> 

<template>
    <form @:submit.prevent="$emit('addTodo', {todo, clear})">
        <h1 class="title">Todo</h1>
        <div class="form-control">
            <label for="todo">Todo :</label>
            <input type="text" name="" v-model="todo" id="todo" placeholder="your todo...." required>
        </div>
        <div style="text-align: end;">
            <button>Add</button>
        </div>
    </form>
</template>