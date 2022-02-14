<template>
  <div>
    <h1>Componente Conteúdo</h1>
    <p>Conteudo - Propriedade $style: {{ $style }}</p>
    <div :class="$style.teste">Class teste-2</div>
    <div :id="$style['teste-2']">ID teste-1</div>
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
<style module>
  .teste {
    background-color: red;
  }
  #teste-2 {
    background-color: yellow;
  }
</style>
