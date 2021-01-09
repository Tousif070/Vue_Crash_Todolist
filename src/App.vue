<template>

  <div id="app" class="container">

    <Header />
    
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />

    <AddTodo v-on:add-todo="addTodo" />
    
  </div>

</template>


<script>
import Header from './components/layouts/Header'
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',

  components: {
    Header,
    Todos,
    AddTodo
  },

  data() {

    return {

      todos: [
        {
          id: 1,
          title: "Clean the room",
          completed: false
        },

        {
          id: 2,
          title: "Buy some snacks",
          completed: false
        },

        {
          id: 3,
          title: "Do some exercise",
          completed: false
        }
      ]

    }

  },

  methods: {

    deleteTodo(id) {

      this.todos = this.todos.filter(todo => todo.id !== id)

    },

    addTodo(newTodo) {

      this.todos = [...this.todos, newTodo]
      
    }

  }

}

</script>
