<template>
  <div>
    <h1>Componente App</h1>
    <topo-padrao @nomeDoEventoQueSeraCapturadoNoComponentePai="$event('Texto 1', 125)"/> <!-- acao($event) caso  opcao seja executar um método daqui do component pai. Recebendo o $event que vem do filho. Caso o $event seja uma funcao de callback a sintaxe muda para $event() , onde indica que é pra executar uma funcao de callback vinda do filho-->
    <button @click="desmontarComponente()">Desmontar o componente Conteúdo</button>
    <conteudo v-if="visibilidade"></conteudo>
  </div>
</template>

<script>
import Conteudo from '@/components/layouts/Conteudo.vue'
import TopoPadrao from '@/components/layouts/TopoPadrao.vue'

export default {
  name: 'App',
  data: () => ({
    visibilidade: true
  }),
  methods: {
    desmontarComponente() {
      this.visibilidade = false;
    },
    acao(event) {
      //console.log('Chegamos até o componente PAI');
      //console.log(event);
      console.log(event.msg);
    }
  },
  components: {
    Conteudo,
    TopoPadrao
  }
}
</script>

<style scoped>
  
</style>
