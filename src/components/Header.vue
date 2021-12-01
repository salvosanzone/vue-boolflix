<template>
  <header class="container-fluid d-flex justify-content-between align-items-center">
    <div class="fs-3">boolflix</div>
    <input  class="form-control" placeholder="Search">
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
      width: 100px;
      height: 20px;
    }

  }
</style>