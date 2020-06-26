<template>
    <div class="content" @click="markComplete">
       <h3 v-bind:class="{done:todo.completed}">{{todo.title}}</h3>
       <button @click="$emit('delete-Todo',todo.id)" class="circular ui icon button negative">
            <i class="icon trash inverted"></i>
       </button>
    </div>
</template>

<script>
export default {
    props:[
        "todo"
    ]
    ,
    methods:{
        markComplete: function(){
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
    .content{
        position: relative;
        padding:5px;
    }
    .circular.ui.icon.button.negative{
        position: absolute;
        top:50%;
        right:0%;
        transform: translate(-50%,-50%);
    }

    h3{
        margin:0;
    }

    .done{
        text-decoration: line-through;
    }
</style>