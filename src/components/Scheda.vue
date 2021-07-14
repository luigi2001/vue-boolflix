<template>
  <section>
      <ul>
          <li><strong>{{dettagli.title || dettagli.name}}</strong></li>
          <li><img :src="`https://image.tmdb.org/t/p/${grandezza}${dettagli.backdrop_path}`" :alt="dettagli.title || dettagli.name"></li>
          <li>{{dettagli.original_title || dettagli.original_name}}</li>
          <li><img class="lingua" :src="lingua(dettagli.original_language)" :alt="dettagli.original_language"></li>
          <li>{{dettagli.vote_average}}</li>
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
        lingua(img) {
      try {
        let nomeimg = require('../assets/' + img + '.png');
        return nomeimg
      } 
      catch{
      }
    }
    }
}
</script>

<style lang="scss">

ul{
    list-style: none;
}

.lingua{
    width: 20px;
}

</style>