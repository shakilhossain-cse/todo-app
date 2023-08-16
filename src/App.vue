<script setup>
import { ref } from 'vue';
import TodoForm from './components/TodoForm.vue';
import TodoList from './components/TodoList.vue';

const todos = ref([]);

const addTodo = (title) => {
  const newTodo = {
    title:title, 
    id:Date.now(),
    isComplete:false
  }
  todos.value.push(newTodo);
};

const removeTodo = (todo) => {
  todos.value = todos.value.filter(item => item.id !== todo.id);
};
</script>


<template>
  <div class="h-[100vh] bg-slate-200 flex items-center justify-center">
    <div class="bg-white rounded shadow p-6 m-4 w-full lg:w-3/4 lg:max-w-lg">
      <TodoForm @add-todo="addTodo" />
      <div v-if="todos.length">
        <TodoList :todos="todos" @remove-todo="removeTodo" />
      </div>
      <p v-else>No data found</p>
    </div>
  </div>
</template>

