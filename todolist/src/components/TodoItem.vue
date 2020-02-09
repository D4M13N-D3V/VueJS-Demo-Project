<template>
    <!--                   binds class to a boolean-->
    <div class="todoItem" v-bind:class="{'isCompleted':todo.completed}">
        <p>
            <!--add event to a method on the component, in this case the change of value event-->
            <input type="checkbox">
            {{todo.title}}
            <!--add event to a method on the component, in this case the click event-->
            <button class="deleteButton">Delete</button>
        </p>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo"]
}
</script>

<style scoped>
  .deleteButton {
    background-color: darkred;
    color: #fff;
    border: none;
    padding: 5px 9px;
    cursor: pointer;
    float: right;
  }
  
  .todoItem {
    background: #000000;
    color: white;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  
  .isCompleted {
    text-decoration: line-through;
  }
</style>