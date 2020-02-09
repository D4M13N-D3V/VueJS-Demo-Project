<template>
    <div class="div">
        <!-- Need to give unique value for key bind -->
        <ul v-bind:key="todo.id" v-for="todo in todos">
            <!--           propname  value-->
            <TodoItem v-bind:todo="todo"/>
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