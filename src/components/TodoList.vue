<template>
    <div class="ui container">
        <Form @addTodo="mark"/>
        <div class="ui middle aligned animated selection list">
            <div v-for="todo in todos" :key="todo.id" class="item">
                <Todo v-bind:todo="todo" @delete-Todo="$emit('delete-Todo',todo.id)"/>
            </div>
        </div>
    </div>
</template>

<script>
import Todo from "./Todo"
import Form from "./Form"

export default {
    props: ['todos'],
    components:{
        Todo
        ,Form
    },
    methods:{
        deleteTodo:()=>{
            console.log('test');
        },
    mark: function(e){
      this.$emit('addTodo',e);
    }
    }
}

</script>

<style scoped>
    .ui.container{
        width:70%!important;
        margin: auto!important;
    }

</style>