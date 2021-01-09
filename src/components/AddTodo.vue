<template>
    
    <form class="row mt-4" v-on:submit="addTodo">

        <div class="col-5">

            <input type="text" v-model="title" name="title" placeholder="Enter a todo here ..." class="form-control">

        </div>

        <div class="col-2">

            <input type="submit" value="Add Todo" class="btn btn-success">

        </div>

    </form>

</template>

<script>

import { v4 as uuidv4 } from 'uuid'

export default {
    name: 'AddTodo',

    data() {
        return {
            title: ""
        }
    },

    methods: {

        addTodo() {
            event.preventDefault()

            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }

            this.$emit('add-todo', newTodo)

            this.title = ""
        }

    }
}

</script>