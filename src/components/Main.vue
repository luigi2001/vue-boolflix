<template>
  <section>
    <Scheda  v-for="film in dettagli" :key="film.id" :dettagli="film"/>
  </section>
</template>

<script>
import Scheda from '@/components/Scheda.vue'
export default {
    name: 'Main',
    components:{
        Scheda
    },
    props: ['dettagli']
}
</script>

<style lang="scss">

</style>