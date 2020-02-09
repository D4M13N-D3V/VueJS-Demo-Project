<template>
    <div class="div">
        <!-- Need to give unique value for key bind -->
        <ul v-bind:key="todo.id" v-for="todo in todos">
            <!--           propname  value-->
            <!-- add a v-on:emittername to catch event and emit again to parent -->
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </ul>
    </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
    name: "Todos",
    props: ["todos"],
    components:{
        TodoItem
    }
}
</script>

<style scoped>

</style>