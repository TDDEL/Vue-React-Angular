<template>
<div>
    <form @submit="addTodo">
        <input type ="text" v-model="title" name="title" placeholder="add todo"/>
        <input type ="submit" name="submit" class="btn"/>
    </form>
</div>
</template>



<script>
export default {
    name:"AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods:{
         addTodo(e){
             e.preventDefault();
             const newTodo={
                 title: this.title,
                 completed: false
            }
            console.log(newTodo)
            this.$emit('add-todo', newTodo)
         }
    }
}
</script>



<style scoped>
form{
    display:flex;
}

input[type ="text"] {
    flex: 10px;
    padding: 5px;
}

input[type="submit"]{
    flex: 2;
}

</style>