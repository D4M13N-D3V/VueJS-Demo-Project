<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <!-- v-bind binds data to the component -->
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
import Header from './components/Header'
import AddTodo from './components/AddTodo'
export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(x=>x.id!=id)
    },
    addTodo(newTodo){
      this.todos.push(newTodo);
    }
  },
  data(){
    return {
      todos : [
        {
            id:1,
            title:"Test 1",
            completed:true
        },
        {
            id:2,
            title:"Test 2",
            completed:false
        },
        {
            id:3,
            title:"Test 3",
            completed:false
        },
        {
            id:4,
            title:"Test 4",
            completed:false
        }
      ]
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
    background-color: black
  }
</style>
