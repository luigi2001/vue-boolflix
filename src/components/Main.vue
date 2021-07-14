<template>
  <section>
    <h3>Film:</h3>
    <Scheda  v-for="film in dettagli" :key="film.id" :dettagli="film"/>
    <h3>Serie tv:</h3>
    <Scheda v-for="serietv in dettagliTv" :key="serietv.id" :dettagli="serietv"/>
  </section>
</template>

<script>
import Scheda from '@/components/Scheda.vue'
export default {
    name: 'Main',
    components:{
        Scheda
    },
    props: ['dettagli', 'dettagliTv']
}
</script>

<style lang="scss">

</style>