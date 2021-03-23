<template>
<div v-if="todos.length > 0" class="mt-10 bg-white dark:bg-navbar-cream dark:text-dark-body-color p-2 m-auto w-4/5 sm:w-3/5 lg:w-2/5 rounded-lg shadow-inner">
  <div v-for="todo in todos" :key="todo.id">
      <TodoItem :todo="todo" @toggleTodoCompleted="toggleCompleted" @emitTodo="getTodo" :deleteTodo="deleteTodo" />
  </div>
</div>

</template>

<script>
import TodoItem from './TodoItem'
export default {
    components: { TodoItem },
    props: ['todos','deleteTodo'],
    methods: {
      toggleCompleted(e) {
        this.$emit('toggleCompleted',e)
      },
      getTodo(e) {
        this.$emit('getTodo',e);
      }
    }

}
</script>

<style>

</style>