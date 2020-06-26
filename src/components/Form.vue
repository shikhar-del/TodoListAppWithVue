<template>
    <div>
        <form class="ui form" @submit="addTodo">
            <div class="field">
                <input type="text" v-model="value" placeholder="Add Todo">
            </div>
            <button class="ui button primary" type="submit">Submit</button>
        </form>
    </div>    
</template>

<script>
export default {
    name:"Form",
    data(){
        return{
            value: ''
        }
    },
    methods:{
        addTodo:function(e){
            e.preventDefault();
            const value = this.value
            this.$emit("addTodo",value)
            this.value = ''
        }
    }
}
</script>

