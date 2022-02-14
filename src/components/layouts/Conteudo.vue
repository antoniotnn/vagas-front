<template>
  <div>
    <h1>Componente Conteúdo</h1>
    <home></home>
    <publicar-vaga></publicar-vaga>
  </div>
</template>

<script>
import Home from '../views/Home.vue'
import PublicarVaga from '../views/PublicarVaga.vue'
  export default {
    name: 'Conteudo',
    components: {
      Home,
      PublicarVaga
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1 {
    color: green;
  }
</style>
