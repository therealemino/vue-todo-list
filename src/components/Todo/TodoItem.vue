<template>
    <div class="m-2 justify-between flex">
        <button @click="toggleComplete" class="rounded-full h-7 w-7 p-2 px-3 m-2 outline-none focus:outline-none" :class="todo.completed ? 'bg-navbar-brown' : 'bg-gray-600'">
        </button> 

        <span class="text-gray-600 text-lg sm:text-2xl dark:text-cream px-2 pt-1.5 overflow-visible" :class="todo.completed ? 'line-through' : 'no-underline'">{{ todo.title }}</span>

        <button @click="emitTodo" class="rounded-full h-7 w-7 pb-1 pt-0.5 pl-2 pr-2.5  m-2 bg-red outline-none focus:outline-none dark:bg-dark-red text-gray-300 dark:text-cream font-mallana">
            <span class="fa fa-trash"></span>
        </button>

    </div>
</template>

<script>
export default {
    props:['todo','deleteTodo'],
    data() {
        return {
            
        }
    },
    computed: {
        
    },
    methods: {
        toggleComplete() {
            // cant do this => this.todo.completed = !this.todo.completed, so we emit the value to the parent component
            // console.log(this.todo); //for debugging
            this.$emit('toggleTodoCompleted',this.todo)
        },
        emitTodo() {
            this.$emit('emitTodo',this.todo)
        }
        
        
    }
}
</script>

<style>

</style>