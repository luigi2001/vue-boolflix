<template>
  <section>
      <h2>Serie tv:</h2>
      <ul>
          <li><strong>{{dettagliTV.name}}</strong></li>
          <li>{{dettagliTv.original_name}}</li>
          <li>{{dettagliTv.original_language}}</li>
          <li>{{dettagliTv.vote_average}}</li>
      </ul>
  </section>
</template>

<script>
export default {
    name: 'SchedaTv',
    props:['dettagliTv']
}
</script>

<style lang="scss">

ul{
    list-style: none;
}

</style>