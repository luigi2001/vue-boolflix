<template>
  <div id="app">
    <Header @cerca="funzionecerca"/>
    <Main :dettagli="films" :dettagliTv="serietv"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from '@/components/Main.vue'
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
        url: 'https://api.themoviedb.org/3/search/movie',
        urltv: 'https://api.themoviedb.org/3/search/tv',
        apikay: 'de40df7a2116a079f9dae2ae8c6df158',
        language: 'it-IT',
        films: [],
        serietv: []
      }
  },
  methods:{
    funzionecerca(testocerca){
      axios
           .get(this.url, {
             params:{
               api_key: this.apikay,
               query: testocerca,
               language: this.language
             }
           })
           .then(risposta =>{
             this.films = risposta.data.results;
           });
      axios
           .get(this.urltv, {
             params:{
               api_key: this.apikay,
               query: testocerca,
               language: this.language
             }
           })
           .then(risposta=>{
             this.serietv = risposta.data.results;
           })     
    }
  }
  
}
</script>

<style lang="scss">
@import '@/style/global.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
