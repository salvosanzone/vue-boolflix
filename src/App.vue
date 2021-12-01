<template>
  <div>
    <Header />
    <Main />
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
  }
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
@import '~@fontsource/bebas-neue/index.css';

</style>
