<template>
    
    <div class="row mt-4">
        
        <div class="col-11">

            <label style="cursor: pointer;">

                <span v-if="todo.completed === true">

                    <input type="checkbox" checked v-on:change="markComplete" style="cursor: pointer;">

                </span>

                <span v-else>

                    <input type="checkbox" v-on:change="markComplete" style="cursor: pointer;">

                </span>

                <span v-bind:class="{'is-complete': todo.completed}">

                    {{ todo.title }}

                </span>

            </label>

        </div>

        <div class="col-1">

            <button class="btn btn-danger" v-on:click="$emit('delete-todo', todo.id)" style="font-size: 16px; padding: 1px 8px;">x</button>

        </div>

    </div>

</template>


<script>

export default {
    name: 'TodoItem',

    props: ["todo"],

    methods: {

        markComplete() {
            this.todo.completed = !this.todo.completed
        }

    }
}

</script>


<style scoped>

    .is-complete {
        text-decoration: line-through;
    }

</style>