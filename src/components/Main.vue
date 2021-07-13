<template>
  <section>
    <Scheda  v-for="film in dettagli" :key="film.id" :dettagli="film"/>
    <SchedaTv v-for="serietv in dettagliTv" :key="serietv.id" :dettagliTv="serietv"/>
  </section>
</template>

<script>
import Scheda from '@/components/Scheda.vue';
import SchedaTv from '@/components/SchedaTv.vue'
export default {
    name: 'Main',
    components:{
        Scheda,
        SchedaTv
    },
    props: ['dettagli', 'dettagliTv']
}
</script>

<style lang="scss">

</style>