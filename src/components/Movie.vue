<template>

     <div class="movie">
       <ul class="p-2">
         <li>{{movieData.title}}</li>
         <li>{{movieData.original_title}}</li>
         <li>
           <img :src="require(`../assets/img/${movieData.original_language}.png`)" alt="movieData.original_language">
         </li>
         <li>{{movieData.vote_average}}</li>
       </ul>
     </div>
  
</template>

<script>
export default {
  name: 'Movie',
  props: {
    movieData: Object
  },
  data(){
    return{
      urlImg: 'https://image.tmdb.org/t/p/w342/',
    }
    
  }
}
</script>

<style lang="scss">
  .movie{
    border: 1px solid white;
    height: 300px;
    width: calc(100% / 5 - 10px);
    margin: 5px;
    ul li{
      list-style: none;
      color: white;
      img{
        width: 10%;
      }
    }
  }
</style>