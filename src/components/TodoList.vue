
<script setup>
import { defineProps, defineEmits } from 'vue';

const emit = defineEmits(['remove-todo']);
const props = defineProps({
  todos: Array
});

const handleRemoveClick = (todo) => {
  emit('remove-todo', todo);
};


const toggleDone = (todo) => {
  todo.isComplete = !todo.isComplete;
};

</script>

<template>
    <div>
      <div v-for="todo in todos" :key="todo.id" class="flex mb-4 items-center">
        <p :class="{'w-full text-grey-darkest': !todo.isComplete, 'w-full line-through text-green': todo.isComplete}">
          {{ todo.title }}
        </p>
        <button
          class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-black"
          @click="toggleDone(todo)"
        >
          Done
        </button>
        <button
          @click="handleRemoveClick(todo)"
          class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-black hover:bg-red"
        >
          Remove
        </button>
      </div>
    </div>
  </template>
  
  
