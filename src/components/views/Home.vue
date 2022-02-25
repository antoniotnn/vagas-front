<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga></pesquisar-vaga>
      </div>
    </div>

    <lista-vagas />

    <div class="row mt-5">
      <div class="col col-4">
        <indicador titulo="Vagas abertas" :indicador="100" bg="bg-dark" color="text-white"></indicador>
      </div>

      <div class="col col-4">
        <indicador titulo="Profissionais cadastrados" :indicador="225" bg="bg-dark" color="text-white"></indicador>
      </div>

      <div class="col col-4">
        <indicador titulo="Visitantes online" :indicador="usuariosOnline" bg="bg-light" color="text-dark"></indicador>
        <!--{{ usuariosOnline }}-->
      </div>
    </div>
  </div>
</template>

<script>

  import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue';
  import Indicador from '@/components/comuns/Indicador.vue';
  import ListaVagas from '@/components/comuns/ListaVagas.vue';

  export default {
    name: 'Home',
    components: {
      PesquisarVaga,
      Indicador,
      ListaVagas
    },
    data: () => ({
      usuariosOnline: 0,
    }),
    methods: {
      getUsuariosOnline() {
        this.usuariosOnline = Math.floor(Math.random() * 101); // entra 0 e 100
      }
    },
    created() {
      setInterval(this.getUsuariosOnline, 1000) //declarar this.getUsuariosOnline() com o parêntese irá passar o resultado da funçao. Sem o parêntese indica que é pra executar a função.
      // a cada 1 segundo executar a função.
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
