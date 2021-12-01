<template>
  <main class="p-1">
   <div class="container d-flex flex-wrap">
     <Movie 
      v-for="movie in nameOfMovie" 
      :key="movie.id"
      :movieData="movie"
     />
   </div>
    
  </main>
 
</template>

<script>
import Movie from './Movie.vue'
export default {
  name: 'Main',
  components: {
    Movie
  },
  props:{
    //è l'array movies
    nameOfMovie: Array
  },
}

</script>

<style lang="scss">
  main{
    min-height: calc(100vh - 50px);
    background-color: #434343;
    }
   
  
</style>