<template>
  <main class="p-1">
   <div class="container d-flex flex-wrap">
     <Movie
      v-for="movie in movies" :key="movie.id"
      :movieData="movie"
      />
   </div>
    
  </main>
 
</template>

<script>
import axios from 'axios';
import Movie from './Movie.vue'
export default {
  name: 'Main',
  components: {
    Movie
  },
  data(){
    return{
      apiKey: '0a07ff8bc4274aef9e9b7565c4c2e71d',
      apiUrl: 'https://api.themoviedb.org/3/search/movie?api_key=0a07ff8bc4274aef9e9b7565c4c2e71d&query=la dolce vita& language=it-IT',
      movies: []
    }
  },
  methods:{
    //chiamata API
    getApi(){
      axios.get(this.apiUrl)
       .then(response => {
         this.movies = response.data.results;
         console.log('Il mio Array', this.movies);
       })
    .catch(error => {
         console.log(error);
       })
    }
  },
  mounted(){
    this.getApi();
  },
}

</script>

<style lang="scss">
  main{
    min-height: calc(100vh - 50px);
    background-color: #434343;
    }
   
  
</style>