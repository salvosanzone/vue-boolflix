<template>

     <div class="serie">
       <ul class="p-2">
         <li>{{serieData.name}}</li>
         <li>{{serieData.original_name}}</li>
         <li>{{serieData.original_language}}</li>
         <li>{{serieData.vote_average}}</li> 
       </ul>
     </div>
  
</template>

<script>
export default {
  name: 'Serie',
  props: {
    serieData : Object
  }
}
</script>

<style lang="scss">
  .serie{
    border: 1px solid black;
    height: 300px;
    width: calc(100% / 5 - 10px);
    margin: 5px;
    ul li{
      list-style: none;
      color: white;
    }
  }
</style>