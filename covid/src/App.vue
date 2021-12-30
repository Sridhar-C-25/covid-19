<template>
  <Header />
  <Home />
</template>

<script>
import Header from './components/Header'
import Home from '../src/view/Home'
export default {
  
  components:{
    Header,
    Home
  }
}
</script>

<style>
*{
  margin:0;
  padding: 0;
  box-sizing: border-box;
  font-family: Poppins;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #111;
}

</style>
