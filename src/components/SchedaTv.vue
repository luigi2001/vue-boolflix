<template>
  <section>
      <h6>Serie tv:</h6>
      <ul>
          <li><strong>{{dettagliTv.name}}</strong></li>
          <li>{{dettagliTv.original_name}}</li>
          <li><img :src="lingua(dettagliTv.original_language)" :alt="dettagliTv.original_language"></li>
          <li>{{dettagliTv.vote_average}}</li>
      </ul>
  </section>
</template>

<script>
export default {
    name: 'SchedaTv',
    props:['dettagliTv'],
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