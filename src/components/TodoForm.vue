<script setup>
import { ref,defineEmits } from "vue";
const todoInput = ref("");
const inputError = ref("");
const emit = defineEmits(['addTodo'])

const handelSubmit = () => {
  if (!todoInput.value) {
    inputError.value = "input field cannot be empty";
    return;
  }
  emit('addTodo', todoInput.value)
  todoInput.value = ""
  inputError.value = "";
};



</script>

<template>
  <div class="mb-4">
    <h1 class="text-grey-darkest">Todo List</h1>
    <form @submit.prevent="handelSubmit" class="flex mt-4">
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 mr-4 text-grey-darker"
        :class="inputError ? 'ring-red-500' : ''"
        placeholder="Add Todo"
        v-model="todoInput"
      />
      <button
        class="flex-no-shrink p-2 border-2 rounded text-teal border-teal hover:text-black"
        type="submit"
      >
        Add
      </button>
    </form>
    <p class="text-red-500">{{ inputError }}</p>
  </div>
</template>
