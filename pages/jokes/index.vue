<template>
  <div>
    <SearchJokes v-on:search-text='searchText'/>
   <Joke v-for='joke in jokes' :key='joke.id' :joke='joke.joke' :id='joke.id'/>
  </div>
</template>

<script>
import Joke from '../../components/joke';
import SearchJokes from '../../components/SearchJokes';


export default {
  components:{
    Joke,
    SearchJokes
  },
  data(){
    return{
      jokes:[]
    }
  },
  async created(){
    const config = {
      headers: {
        'Accept': 'application/json'
      },
    }
    try {
      const response = await fetch('https://icanhazdadjoke.com/search', config)
      const data = await response.json()
      this.jokes = data.results;
      console.log(this.jokes)
      
    } catch (error) {
      console.log(error)
      
    }
  },
  methods:{
  async searchText(text){
    const config = {
      headers: {
        'Accept': 'application/json'
      },
    }
    try {
      const response = await fetch(`https://icanhazdadjoke.com/search?term=${text}`, config)
      const data = await response.json()
      this.jokes = data.results;
      console.log(this.jokes)
      
    } catch (error) {
      console.log(error)
      
    }
  }
  },

  head(){
    return{
      title: 'Dad JOkes',
      meta:[
        {
          hid: 'description',
          name:'description',
          content:'best place for dad jokes'
        }
      ]

    }
  }

}
</script>

<style>

</style>