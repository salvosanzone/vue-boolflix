<template>
  <header class="container-fluid d-flex justify-content-between align-items-center">
    <div class="fs-3">boolflix</div>
    <div class="d-flex align-items-center">
      <input  class="form-control" placeholder="Search Movies">
      <button type="button" class="btn btn-light d-flex align-items-center">Search</button>
    </div>
    
  </header>
</template>

<script>
export default {
  name: 'Header'
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