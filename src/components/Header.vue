<template>
  <header class="container-fluid d-flex justify-content-between align-items-center">
    <div class="fs-3">boolflix</div>
    <div class="d-flex align-items-center">
      <input 
        @keyup.enter="getMoviesTvSeries"
        v-model="titleOfMovieTvSeries"
        class="form-control" 
        placeholder="Search Movie"
      >
      <button @click="getMoviesTvSeries"
        type="button" 
        class="btn 
        btn-light d-flex 
        align-items-center"
      >
        Search
      </button>
    </div>
    
  </header>
</template>

<script>
export default {
  name: 'Header',
  data(){
    return{
      //qui inserisco il titolo del film
      titleOfMovieTvSeries: ''
    }
  },
  methods:{
    //(il click scatena tutto) al click partità la chiamata
    getMoviesTvSeries(){
      console.log('click');
      console.log('Header sta facendo partire un evento  ->', this.titleOfMovieTvSeries);
      this.$emit('clickEvent', this.titleOfMovieTvSeries);
      //resetto l'input
      this.titleOfMovieTvSeries = '';
    }
  },

}
</script>

<style lang="scss">
  header{
    height: 50px;
    background-color: black;
    color: #B30000;
    .form-control{
      width: 200px;
      height: 20px;

    }
    .btn{
      height: 20px;
      margin-left: 10px;

    }
  }
</style>