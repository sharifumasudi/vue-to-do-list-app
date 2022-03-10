<template>
  <div id="app">
    <ToDOList/>
    <Footer/>
  </div>
</template>

<script>
import ToDOList from './components/ToDOList.vue';
import Footer from '@/components/Footer';
import './assets/tailwind.css';
export default {
  name: 'App',
  components: {
    ToDOList,
    Footer
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
