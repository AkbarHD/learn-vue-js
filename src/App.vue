<script setup> // tambahkan setup untuk bisa mengakses variabel
// const hello = "hello";
// utk mengakses ini perlu v-bind
// const green = "green"; 
// console.log(hello);
import FormTodo from './components/FormTodo.vue'; // ini menggunakan component
import { ref } from 'vue';  // import dlu agar bisa menggunakan ref

// Ketika datanya berubah maka vue akan mengupdate domnya
const todos = ref([]); // ini namanya state, bukan variable lagi

function add(data) { // harus sama dengan yang ada di FormTodo
  // console.log(data.todo); // todo dapat dari FormTodo.vue
  todos.value.push({ id: crypto.randomUUID(), todo: data.todo });
  data.clear(); // ketika datanya berhasil ditambahkan, clear formnya
}
</script>

<template>
  <!-- <h1 v-bind:style="{color: green}">Hello World {{ hello }}</h1> -->
   <section class="wrapper">
    <FormTodo  @add-todo="add"/> <!-- ini menggunakan component -->
   </section>
</template>

 <!-- scoped ini dia menjadi tidak global, kalo tidak ada scoped dia global --> 
<style scoped> 
  /* .warna{
    color: blue;
  } */
   .wrapper{
    display: flex;
    flex-direction: column;
    height: 100svh;
    justify-content: center;
    align-items: center;
   }
</style>