<template>
<div class="w-4/5 sm:w-1/3 mx-auto mt-32">
  <input type="text" placeholder="Add New Item" v-model="newTodo" class="w-3/4 p-4 rounded-md outline-none overflow-x-auto focus:shadow-blur dark:focus:shadow-dark-blur transition-shadow">
  <button @click="addTodo" class="bg-gray-700 dark:bg-navbar-brown ml-2 w-1/5 text-gray-300 dark:text-cream p-2 rounded-lg outline-none focus:outline-none">Add</button>
  <!-- <div>{{ newTodo }}</div> -->
</div>

</template>

<script>
export default {
    'Name':'AddTodo',
    props:['todos'],
    data() {
      return {
        newTodo: ''
      }
    },
    methods: {
      addTodo() {
        this.$emit('addTodo',this.newTodo)
        this.newTodo = ''
      }
    }

}
</script>

<style>

</style>
