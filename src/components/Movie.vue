<template>
     <div class="movie">
       <ul class="p-2">
         <li >Titolo: {{movieData.title}}</li>
         <li>Titolo Originale: {{movieData.original_title}}</li>
         <li>Lingua: {{movieData.original_language}}</li>
         <li>Voto: {{movieData.vote_average}}</li>
       </ul>
     </div>
  
</template>

<script>
export default {
  name: 'Movie',
  props: {
    movieData : Object
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
    }
  }
</style>