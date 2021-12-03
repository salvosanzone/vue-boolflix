<template>

  <main class="p-1">
    <h2 class="m-5" v-if="searchList != ''">
      {{ titleSection }}
    </h2>
    <div class="container d-flex flex-wrap">
      <Card 
      v-for="item in searchList" 
      :key="item.id" 
      :itemData="item" 
      />
    </div>

      <!-- <section class="d-flex justify-content-center align-items-center">
        <div
        v-for="movie in ListOfBestMovies" 
        :key="movie.id" 

        class="container-ss "
        >
          
        </div>
      </section> -->
      

  </main>

</template>

<script>
import axios from 'axios';
import Card from "./Card.vue";
export default {
  name: "Main",
  components: {
    Card,
  },
  props: {
    searchList: Array,
    titleSection: String,
  },
  data() {
    return {
      ListOfBestMovies: []
    }
  },
  mounted(){
    axios.get('https://api.themoviedb.org/3/search/movie?api_key=0a07ff8bc4274aef9e9b7565c4c2e71d&language=it-IT&query=la dolce vita')
    .then(response => {
        this.ListOfBestMovies = response.data.results
        console.log('ListOfBestMovies ->',response.data.results);
      }).catch( error => {
          console.log(error);
      })
  }
};
</script>

<style lang="scss">
main {
  min-height: calc(100vh - 60px);
  background: linear-gradient(#424242, #434343);
  section{
    height: 100vh;
  }
  .container-ss{
    width: 500px;
    height: 200px;
    border: 1px solid black;
  }
}
</style>