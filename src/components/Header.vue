<template>
<nav class="navbar navbar navbar-dark bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand text-danger uppercase">BoolFlix</a>
    <form class="d-flex">
      <input class="form-control me-2" type="text" placeholder="Cerca film o serie tv" v-model="cerca">
      <button class="btn btn-outline-success text-danger border-danger" @click.prevent="$emit('cerca',cerca)">Cerca</button>
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
.uppercase{
  text-transform: uppercase;
}
</style>