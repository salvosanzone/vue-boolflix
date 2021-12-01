<template>
  <header class="container-fluid d-flex justify-content-between align-items-center">
    <div class="fs-3">boolflix</div>
    <div class="d-flex align-items-center">
      <input v-model="titleOfMovie"
        class="form-control" 
        placeholder="Search Movie"
      >
      <button @click="getMovies"
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
      titleOfMovie: ''
    }
  },
  methods:{
    //(il click scatena tutto) al click partità la chiamata, che verrà effettuata da App passatogli tramite un emit,poiche App rimarrà in ascolto di qualcosa trasmesso da Header
    getMovies(){
      console.log('click');
      console.log('Header sta facendo partire un evento  ->', this.titleOfMovie);
      this.$emit('clickEvent', this.titleOfMovie);
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