<template>
    <div class="ui inverted segment">
        <h2 class="ui grey inverted header center aligned">TODOS</h2>
        <div id="nav">
            <router-link class="link" to="/">Home</router-link> |
            <router-link class="link" to="/about">About</router-link>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .ui.inverted.segment{
        border-radius: 0px;
    }
    #nav{
        text-align: center;
        color:aliceblue;
    }
    .link{
        color: aliceblue;
    }
</style>