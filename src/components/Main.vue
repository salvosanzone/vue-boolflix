<template>
  <main class="p-1">
   <div class="container d-flex flex-wrap">
     <Movie />
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
    //nameOfMovie: String
  },
}

</script>

<style lang="scss">
  main{
    min-height: calc(100vh - 50px);
    background-color: #434343;
    }
   
  
</style>