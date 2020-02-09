<template>
  <div id="app">
    <!-- v-bind binds data to the component -->
    <Todos v-bind:todos="todos"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
export default {
  name: 'App',
  components: {
    Todos
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
  }
</style>
