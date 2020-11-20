<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
       <input type="checkbox" v-on:change="markComplete"> {{todo.title}}
       <button class="del" v-on:click="$emit('del-todo', todo.id)"></button>
    </p>
  </div>
</template>



<script>
export default {
    name:"ToDoItem",
    props:["todo"],
    methods: {
      markComplete(){
        this.todo.completed = !this.todo.completed
      }
    }
}
</script>



<style scoped>
.todo-item {
    background: rgb(151, 8, 8);
    padding: 10px;
    border-bottom: 1px seagreen;
}

.is-complete {
    text-decoration: line-through;
}

.del {
    background: red;
    color: white;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
</style>