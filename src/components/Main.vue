<template>
  <main class="p-1">

     <h2 class="m-5" v-if="searchList != ''">
      {{titleSection}}
    </h2> 
    <div class="container d-flex flex-wrap">
     <Card 
      v-for="item in searchList" 
      :key="item.id"
      :itemData="item"
     />
    </div>

  </main>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'Main',
  components: {
    Card,
  },
  props:{
    searchList: Array,
    titleSection: String
  },
  data(){
    return{

    }
  },
 
  }


</script>

<style lang="scss">
  main{
    min-height: calc(100vh - 60px);
    background: linear-gradient(#424242, #434343);
  }
   
  
</style>