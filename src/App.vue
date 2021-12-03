<template>
  <div>
    <Header @clickEvent="searchMoviesTvSeries"/>
    <Main :searchList="ListOfmovies" titleSection="movies"/>
    <Main :searchList="ListOfSeries" titleSection="series"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      apiUrlMovie: 'https://api.themoviedb.org/3/search/movie',
      apiUrlTv: 'https://api.themoviedb.org/3/search/tv',
      params:{
        api_key: '0a07ff8bc4274aef9e9b7565c4c2e71d',
        language: 'it-IT',
        query: '',
      },
      ListOfmovies: [],
      ListOfSeries: [],
    }
},
  methods:{
    //la funzione riceve il parametro inviato dall'emit (puo avere un nome anche diverso)
    searchMoviesTvSeries(titleOfMovieTvSeries){

      //MOVIES
      console.log('App ha ricevuto dall evento clickEvent ->', titleOfMovieTvSeries);
      this.params.query = titleOfMovieTvSeries;
      axios.get(this.apiUrlMovie,{params:this.params})
      .then(response => {
        this.ListOfmovies = response.data.results
        console.log('ListOfmovies ->',response.data.results);
      }).catch( error => {
          console.log(error);
      }),


      //TV SERIES
      axios.get(this.apiUrlTv,{params:this.params})
      .then(response => {
        this.ListOfSeries = response.data.results
        console.log('ListOfSeries ->',response.data.results);
      }).catch( error => {
          console.log(error);
      })
    },
    

  },
  
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
@import '~@fontsource/bebas-neue/index.css';

</style>
