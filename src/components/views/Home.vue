<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga></pesquisar-vaga>
      </div>
    </div>

    <div class="row mt-5">
      <div class="col col-4">
        <indicador titulo="Vagas abertas" indicador="100"></indicador>
      </div>

      <div class="col col-4">
        <indicador titulo="Profissionais cadastrados" indicador="225"></indicador>
      </div>

      <div class="col col-4">
        <indicador titulo="Visitantes online" indicador="25"></indicador>
      </div>
    </div>
  </div>
</template>

<script>

  import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue';
  import Indicador from '@/components/comuns/Indicador.vue';

  export default {
    name: 'Home',
    components: {
      PesquisarVaga,
      Indicador
    },
    activated() {
      console.log('Componente ativado')
    },
    deActivated() {
      console.log('Componente desativado')
    },
    beforeUnmount() {
      console.log('Antes de desmontar/destruir')
    },
    unmounted() {
      console.log('Desmontado/destruído')
    },
    created() {
      console.log('Criado', this.teste);
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
