<template>
<nav class="main-nav">
    <router-link :to="{name:'Home'}">Project</router-link>
    <router-link :to="{name:'AddProject'}">Add A New Project</router-link>
</nav>
    
</template>
<script>
export default {
    
}
</script>
<style>
.main-nav{
    text-align: center;
    margin: 30px auto;
}
.main-nav a{
    text-decoration: none;
    display: inline-block;
    margin: 0 10px;
    font-size: 18px;
    color: black;
}
a.router-link-active{
    border-bottom:2px solid rgb(29, 216, 36);
    padding-bottom: 4px;

}

</style>


