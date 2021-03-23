<template>
<div>
    <Navbar :darkMode="darkMode" :changeDarkMode="changeDarkMode" /> 
    <AddTodo :todos="todos" @addTodo="addTodo" />
    <TodoList :todos="todos" @toggleCompleted="toggleComplete" @getTodo="deleteTodo" :deleteTodo="deleteTodo" />
    <div class="pb-16"></div>
    <Footer />    
</div>
</template>

<script>
import Navbar from './components/Navbar'
import TodoList from './components/Todo/TodoList'
import AddTodo from './components/Todo/AddTodo'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Navbar,TodoList,AddTodo,Footer
  },
  data() {
    return {
      darkMode: false,
      todos: [
        {
          id: 1,
          title: "First Task",
          completed: false,
          category:"personal"
        }
      ]
    }
  },
  computed: {
     
  },
  methods: {
        changeDarkMode () {//toggles the state of the darkmode to true or false
            this.darkMode = !this.darkMode
            this.setDarkMode()
        },
        setDarkMode() { //adds the dark class to the html tag (required for the dark-mode styling to work in tailwind)
          const root = document.documentElement
          root.classList.toggle('dark')
        },
        toggleComplete(e) {
          // console.log(e.completed)
          e.completed = !e.completed
        },
        deleteTodo(e) {
          // console.log(e.id);
          const id = e.id
          const filteredArray = this.todos.filter(item => item.id !== id)
          this.todos = filteredArray
        },
        addTodo(e) {
          // console.log(e);
          if(e.length >= 1) {
            this.todos.push({
              id: this.todos.length + 1,
              title: e,
              completed: false,
              category:"personal"
          })
          }
          
        }
        
        
    }

}
</script>


<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
