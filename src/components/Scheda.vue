<template>
  <section>
      <h6>Film:</h6>
      <ul>
          <li><strong>{{dettagli.title}}</strong></li>
          <li>{{dettagli.original_title}}</li>
          <li><img :src="lingua(dettagli.original_language)" :alt="dettagli.original_language"></li>
          <li>{{dettagli.vote_average}}</li>
      </ul>
  </section>
</template>

<script>
export default {
    name: 'Scheda',
    props:['dettagli'],
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

img{
    width: 20px;
}

</style>