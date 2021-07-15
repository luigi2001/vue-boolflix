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

    const request = {
      params:{
          api_key: this.apikay,
          query: testocerca,
          language: this.language
        }
    };
      axios
           .all([
             axios.get(this.url, request),
             axios.get(this.urltv, request)
           ])
           .then(axios.spread((rispostaFilm,rispostaTv) =>{
             this.films = rispostaFilm.data.results;
             this.serietv = rispostaTv.data.results
           }))
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
