<template>
<nav class="navbar navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand">BoolFlix</a>
    <form class="d-flex">
      <input class="form-control me-2" type="text" placeholder="Cerca" v-model="cerca">
      <button class="btn btn-outline-success" @click.prevent="$emit('cerca',cerca)">Cerca</button>
    </form>
  </div>
</nav>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            cerca: ''
        }
    }
}
</script>

<style lang="scss">

</style>