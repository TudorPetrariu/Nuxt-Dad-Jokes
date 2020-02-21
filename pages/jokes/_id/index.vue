<template>
<div>
<nuxt-link to='/jokes'> Back to JOkes</nuxt-link>
<h2>{{joke}}</h2>
<hr>
<small>Joke ID : {{$route.params.id}}</small>
  </div>
</template>

<script>
export default {
    data(){
        return{
            joke:{}
        }
    },
    async created(){
        const config= {
            headers:{
                'Accept': 'application/json'
            }
        }
        try{
        const response= await fetch(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
        const data = await response.json();
        this.joke= data.joke;
        console.log(this.joke)
       } 
        catch(err){
        console.log(err)
    }
    }
}
</script>

<style>

</style>