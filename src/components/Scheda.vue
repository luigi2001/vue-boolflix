<template>
  <section @mouseover="hover = true" @mouseleave="hover = false">
    <img :src="`https://image.tmdb.org/t/p/${grandezza}${dettagli.backdrop_path}`" :alt="dettagli.title || dettagli.name">
    <div class="box text-light" v-if="hover">
      <h3><strong>{{dettagli.title || dettagli.name}}</strong></h3>
      <h4>{{dettagli.original_title || dettagli.original_name}}</h4>
      <img class="lingua" :src="require(`../assets/${dettagli.original_language}.png`)" :alt="dettagli.original_language">
      <span class="d-block"><i class="fas fa-star text-warning" v-for="(stella,index) in stelle(dettagli.vote_average)" :key="index"></i></span>
      <p>{{dettagli.overview}}</p>
    </div>
  </section>
</template>

<script>
export default {
    name: 'Scheda',
    props:['dettagli'],
    data(){
      return{
        grandezza:'w342',
        hover: false
      }
    },
    methods:{
      stelle(voto){
        return parseInt(Math.round(voto / 2))
      }
    }
    
}
</script>

<style lang="scss">
.lingua{
  width: 20px;
}
</style>