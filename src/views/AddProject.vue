<template>
<form @submit.prevent="handlesubmit">

    <label>Title:</label>
    <input type="text" v-model="title" required>
    <label>Details:</label>
    <textarea v-model="details" required></textarea>
    <button>Add Project</button>
</form>
    
</template>
<script>
export default {
    data(){
        return{
            title:'',
            details:''
        }
    },
    methods:{
        handlesubmit(){
           let project={
               title:this.title,
               details:this.details,
               complete:false
           }
           fetch('http://localhost:3000/projects',{
               method:'POST',
               headers:{'Content-type':'application/json'},
               body:JSON.stringify(project)
           })
           .then(()=>{
               this.$router.push('/')
           })
           .catch(err=>console.log(err))
        }
    }
    
}
</script>
<style>
form{
    background:#CCFF99;

    padding: 20px;
    border-radius: 10px;
}
label{
    display: block;
    color: grey;
    text-transform: uppercase;
    font-size: 10px;
    font-weight: bold;
    letter-spacing: 1px;
    margin: 15px 0 10px 0;
    
}
input{
    padding: 10px;
    border: 0;
    border-bottom: 1px solid grey;
    width: 100%;
    box-sizing: border-box;
    border-radius: 10px;
}
textarea{
    padding: 10px;
    border: 0;
    border-bottom: 1px solid grey;
    width: 100%;
    box-sizing: border-box;
    height: 100%;
    border-radius: 10px;


}
form button{
    display: block;
    margin: 20px auto 0;
    background: rgb(17, 105, 105);
    color: white;
    padding: 10px;
    border-radius: 10px;
    border: 0;
    font-size: 12px;
}
</style>


