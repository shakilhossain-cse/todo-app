<script setup>
import { ref } from "vue";
import TodoForm from "./components/TodoForm.vue";
import TodoList from "./components/TodoList.vue";

const todos = ref([]);
const AddTodo = (todo) => {
  todos.value.push(todo)
};
</script>

<template>
  <!-- component -->
  <div
    class="h-[100vh] bg-slate-200 w-full flex items-center justify-center bg-teal-lightest font-sans"
  >
    <div class="bg-white rounded shadow p-6 m-4 w-full lg:w-3/4 lg:max-w-lg">
      <TodoForm @add-todo="AddTodo"/>
      <TodoList :todos="todos"/>
    </div>
  </div>
</template>
