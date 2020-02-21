<template>
  <form @submit.prevent='onSubmit'>
      <input type="text" v-model='text' placeholder="Search JOkes...">
      <input type="submit" value="Search JOkes">  </form>
</template>

<script>
export default {

name:'SearchJokes',
data(){
    return{
        text: ''
    }
},
methods:{
    onSubmit(){
        this.$emit('search-text', this.text)
        this.text= '';
    }
}
}
</script>

<style>

</style>