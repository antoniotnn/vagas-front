<template>
  <div>
    <topo-padrao @navegar="componente = $event" /> <!-- capturando evento navegar emitido pelo componente topo padrao, e recuperando o evento emitido atraves do $event (no caso o segundo parâmetro que o topo padrao emite, que é uma string com 'Home', ou 'PublicarVaga' por exemplo e atribuindo para a propriedade componente definido aqui no data deste componente Pai, App) -->
    <conteudo v-if="visibilidade" :conteudo="componente"></conteudo>
  </div>
</template>

<script>
import Conteudo from '@/components/layouts/Conteudo.vue'
import TopoPadrao from '@/components/layouts/TopoPadrao.vue'

export default {
  name: 'App',
  data: () => ({
    visibilidade: true,
    componente: 'Home'
  }),
  components: {
    Conteudo,
    TopoPadrao
  }
}
</script>

<style scoped>
  
</style>
