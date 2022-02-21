<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga></pesquisar-vaga>
      </div>
    </div>

    <div class="row mt-5">
      <div class="col col-4">
        <div class="h-100 p-5 rounded-3 border bg-dark text-white">
          <p>Vagas Abertas</p>
          <h2>25</h2>
        </div>
      </div>

      <div class="col col-4">
        <div class="h-100 p-5 rounded-3 border bg-dark text-white">
          <p>Profissionais cadastrados</p>
          <h2>125</h2>
        </div>
      </div>

      <div class="col col-4">
        <div class="h-100 p-5 rounded-3 border bg-light text-dark">
          <p>Visitantes Online</p>
          <h2>15</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

  import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue';

  export default {
    name: 'Home',
    components: {
      PesquisarVaga
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
