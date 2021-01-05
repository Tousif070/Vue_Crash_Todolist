<template>

  <div id="app" class="container">
    
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
    
  </div>

</template>


<script>

import Todos from './components/Todos'

export default {
  name: 'App',

  components: {
    Todos
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

    }

  }

}

</script>
