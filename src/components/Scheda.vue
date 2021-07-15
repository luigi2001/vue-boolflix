<template>
  <section>
      <ul>
          <li><strong>{{dettagli.title || dettagli.name}}</strong></li>
          <li><img :src="`https://image.tmdb.org/t/p/${grandezza}${dettagli.backdrop_path}`" :alt="dettagli.title || dettagli.name"></li>
          <li>{{dettagli.original_title || dettagli.original_name}}</li>
          <li><img class="lingua" :src="require(`../assets/${dettagli.original_language}.png`)" :alt="dettagli.original_language"></li>
          <li><i class="fas fa-star text-warning" v-for="(stella,index) in stelle(dettagli.vote_average)" :key="index"></i></li>
      </ul>
  </section>
</template>

<script>
export default {
    name: 'Scheda',
    props:['dettagli'],
    data(){
      return{
        grandezza:'w342'
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

ul{
    list-style: none;

  .lingua{
    width: 20px;
  }
}
</style>