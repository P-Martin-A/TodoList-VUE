<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
  import Header from './layouts/Header'
  import Main from './layouts/Main'

  export default {
    name: 'App',
    components: {
      Header,
      Main,
    },
  }
</script>

<style>
  *, *::before, *::after{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  html{
    font-size: 10px;
  }

  body{
    font-family: Avenir, Helvetica, Arial, sans-serif;
  }

  ul li{
    list-style: none;
  }

  a{
    text-decoration: none;
  }
</style>
