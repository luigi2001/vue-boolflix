<template>
  <section>
      <h2>Film:</h2>
      <ul>
          <li><strong>{{dettagli.title}}</strong></li>
          <li>{{dettagli.original_title}}</li>
          <li>{{dettagli.original_language}}</li>
          <li>{{dettagli.vote_average}}</li>
      </ul>
  </section>
</template>

<script>
export default {
    name: 'Scheda',
    props:['dettagli']
}
</script>

<style lang="scss">

ul{
    list-style: none;
}

</style>