<template>
  <div id="home">
    <AddTodo v-on:add-todo="addTodo"/>
    <!-- v-bind binds data to the component -->
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from '../components/Todos'
import AddTodo from '../components/AddTodo'
import axios from 'axios';
export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  methods:{
    deleteTodo(id){
      axios.delete(`http://jsonplaceholder.typicode.com/todos/{$id}`).then( this.todos = this.todos.filter(x=>x.id!=id)).catch(error => console.log(error))
    },
    addTodo(newTodo){
      const {title, completed} = newTodo;
      axios.post('http://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      }).then( response => this.todos.push(response.data)).catch(error => console.log(error))
    }
  },
  //this is called upon creation obviously
  created(){
    //log error if we get error other wise use the dat ato populate todos
    axios.get("http://jsonplaceholder.typicode.com/todos?_limit=5").then(res => this.todos = res.data).catch(error => console.log(error))
  },
  data(){
    return {
      todos : []
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
