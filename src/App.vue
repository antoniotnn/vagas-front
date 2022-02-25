<template>
  <div>
    <vagas-favoritas></vagas-favoritas>
    <topo-padrao @navegar="componente = $event" /> <!-- capturando evento navegar emitido pelo componente topo padrao, e recuperando o evento emitido atraves do $event (no caso o segundo parâmetro que o topo padrao emite, que é uma string com 'Home', ou 'PublicarVaga' por exemplo e atribuindo para a propriedade componente definido aqui no data deste componente Pai, App) -->
    
    <alerta v-if="exibirAlerta">
      <template v-slot:titulo>
        <h5>{{ alerta.titulo }}</h5>
      </template>
      <p>{{ alerta.descricao }}</p>
    </alerta>
    
    <conteudo v-if="visibilidade" :conteudo="componente"></conteudo>
  </div>
</template>

<script>
import Conteudo from '@/components/layouts/Conteudo.vue'
import TopoPadrao from '@/components/layouts/TopoPadrao.vue'
import VagasFavoritas from '@/components/comuns/VagasFavoritas.vue'
import Alerta from '@/components/comuns/Alerta.vue'

export default {
  name: 'App',
  data: () => ({
    visibilidade: true,
    componente: 'Home',
    exibirAlerta: false,
    alerta: { titulo: '', descricao: '' }
  }),
  components: {
    Conteudo,
    TopoPadrao,
    VagasFavoritas,
    Alerta
  },
  mounted() {
    this.emitter.on('alerta', (a) => {
      this.alerta = a;
      this.exibirAlerta = true;

      setTimeout(() => this.exibirAlerta = false, 4000);
      //console.log('Apresentar a mensagem de alerta customizada');
    });
  }
}
</script>

<style scoped>
  
</style>
