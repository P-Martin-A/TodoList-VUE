<template>
  <header class="header">
    <h1 class="title">
      Todo      
      <img src="../assets/logo.png" alt="Vue">
      List
    </h1>
  </header>
</template>

<script>
  export default {
    name: 'Header'
  }
</script>

<style scoped>
  .header{
    background-color: #383838;
    padding: 1rem 0;
    text-align: center;
  }

  .header .title{
    color: #fff;
    font-size: 2.5rem;
  }

  .header .title img{
    width: 2.5rem;
    height: 1.8rem;
  }
</style>
