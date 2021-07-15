<template>
  <section class="container-fluid text-light">
    <h3>Film in base alla tua ricerca:</h3>
      <div class="row">
        <div class="col-2 m-3 p-3" v-for="film in dettagli" :key="film.id">
          <Scheda :dettagli="film"/>
        </div>
      </div>
    <h3>Serie tv in base alla tua ricerca:</h3>
      <div class="row">
        <div class="col-2 m-3 p-3" v-for="serietv in dettagliTv" :key="serietv.id">
          <Scheda :dettagli="serietv"/>
        </div>
      </div>
    <h2 class="uppercase">Alcuni film presenti sulla piattaforma:</h2>
    <div class="row">
      <div class="col-2 m-3 p-3" v-for="film in listaFilm" :key="film.id">
        <Scheda :dettagli="film"/>
      </div>
    </div>
    <h2 class="uppercase">Alcune serie tv presenti sulla piattaforma:</h2>
    <div class="row">
      <div class="col-2 m-3 p-3" v-for="serietv in listaTv" :key="serietv.id">
        <Scheda :dettagli="serietv"/>
      </div>
    </div>
  </section>
</template>

<script>
import Scheda from '@/components/Scheda.vue';
import axios from 'axios'
export default {
    name: 'Main',
    components:{
        Scheda
    },
    data(){
      return{
        grandezza:'w342',
        urlListFilm: 'https://api.themoviedb.org/3/discover/movie',
        urLlistTv: 'https://api.themoviedb.org/3/discover/tv',
        apikay: 'de40df7a2116a079f9dae2ae8c6df158',
        language: 'it-IT',
        listaFilm: [],
        listaTv: []
      }
    },
    props: ['dettagli', 'dettagliTv'],
    created(){
      this.liste();
    },
    methods:{
      liste(){

        const request = {
      params:{
          api_key: this.apikay,
          language: this.language
        }
    };
        axios
             .all([
               axios.get(this.urlListFilm, request),
               axios.get(this.urLlistTv, request)
             ])
             .then(axios.spread((rispostaFilm,rispostaTv) =>{
               this.listaFilm = rispostaFilm.data.results;
               this.listaTv = rispostaTv.data.results
             }))
      }
    }
}
</script>

<style lang="scss">
.uppercase{
  text-transform: uppercase;
}
</style>