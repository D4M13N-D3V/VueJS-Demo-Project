<template>
    <!-- @submit adds event for new submit method -->
    <form class="newTaskForm" @submit="addToDo">
        <!-- v-model is same as ngmodel , binds title to thisname -->
        <input type="text" class="taskInput" v-model="title" name="title" placeholder="Add your new task">
        <input type="submit" value="Submit" class="submitButton">
    </form>
</template>

<script>
import uuid from 'uuid'
export default {
    name:"AddTodo",
    //This data is what the v-model is binding too.
    data(){
        return {
            title: ''
        }
    },
    methods:{
        addToDo(e){
            //prevent from actually submitting form.
            e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            this.title=""
            this.$emit('add-todo', newTodo)
        }
    }
}
</script>

<style scoped>
 .newTaskForm{
    display: flex;
  }
  
  .taskInput {
    flex: 10;
    padding: 5px;
  }
  
  .submitButton {
    background-color: orange;
    color: rgb(0, 0, 0);
    border: none;
    padding: 5px 9px;
    flex:2;
    cursor: pointer;
    float: right;
  }
</style>