<script setup>
    import {defineProps} from 'vue'
    const props = defineProps({
        todos:Array
    })
</script>

<template>
    <div v-for="todo in todos" :key="todo">
        <div class="flex mb-4 items-center">
            <p class="w-full text-grey-darkest">
               {{todo}}
            </p>
            <button
                class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-white text-green border-green hover:bg-green">
                Done
            </button>
            <button class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-white hover:bg-red">
                Remove
            </button>
        </div>
        <!-- <div class="flex mb-4 items-center">
            <p class="w-full line-through text-green">
                Submit Todo App Component to Tailwind Components
            </p>
            <button
                class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-white text-grey border-grey hover:bg-grey">
                Not Done
            </button>
            <button class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-white hover:bg-red">
                Remove
            </button>
        </div> -->
    </div>
</template>
