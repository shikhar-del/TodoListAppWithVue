<template>
  <div id="app">
    <TodoList v-bind:todos="todos" @delete-Todo = "del_todo" @addTodo="mark"/>
  </div>
</template>

<script>

import TodoList from "../components/TodoList"
import axios from "axios"

export default {
  name: 'Home',
  components:{
    TodoList
  },  
  data(){
    return{
      todos: [
      ]
    }
  },
  methods:{
    del_todo: function(e){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${e}`)
      .then(this.todos = this.todos.filter(todo => todo.id !== e))
      .catch(err => console.log(err))
    },
    mark: function(e){
      axios.post('https://jsonplaceholder.typicode.com/todos',
      {
        title:e,
        completed:false
      }
      )
      .then(res => this.todos = [...this.todos,res.data])
      .catch(err=>console.log(err))
    }
  },
  created:function(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res=> this.todos = res.data)
    .catch(err=>console.log(err))
  }
}
</script>

<style>
  *{
    margin:0;
    padding: 0;
    font-size: 18px;
    color:black;
  }
</style>
