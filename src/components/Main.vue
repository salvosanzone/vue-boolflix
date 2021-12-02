<template>
  <main class="p-1">

    <h2 class="m-5" v-if="movies != ''">
      movies
    </h2>
    <div class="container d-flex flex-wrap">
     <Movie 
      v-for="movie in movies" 
      :key="movie.id"
      :movieData="movie"
     />
    </div>

    <h2 class="m-5" v-if="series != ''">
      series tv
    </h2>
    <div class="container d-flex flex-wrap">
     <Serie
      v-for="serie in series" 
      :key="serie.id"
      :serieData="serie"
     />
    </div>

  </main>
 
</template>

<script>
import Movie from './Movie.vue';
import Serie from './Serie.vue';
export default {
  name: 'Main',
  components: {
    Movie,
    Serie
  },
  props:{
    movies: Array,
    series: Array
  },
  data(){
    return{

    }
  },
  methods: {
    //creo una funzione in cui do come parametro item(il film o la serie)
    //condizione if, se item.original_language include IT allora item.original_language = alla bandiera dell'italia, stessa cosa per quella dell' inghilterra
    //se item.original_language non include IT o EN allora stampa l'array movies

    filterdList(item){
      if(item.original_language != 'it'){
        return this.movies;
      }
      return this.movies.filter(movie => {
        return movie.original_language === 'it.png';
      })
    }
  }
  }


</script>

<style lang="scss">
  main{
    min-height: calc(100vh - 50px);
    background-color: #434343;
  }
   
  
</style>