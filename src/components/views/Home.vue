<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga></pesquisar-vaga>
      </div>
    </div>

    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <!--{{vaga}}-->
        <vaga v-bind="vaga"/>
      </div>
    </div>

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
  import Vaga from '@/components/comuns/Vaga.vue';

  export default {
    name: 'Home',
    components: {
      PesquisarVaga,
      Indicador,
      Vaga
    },
    data: () => ({
      usuariosOnline: 0,
      vagas: []
    }),
    methods: {
      getUsuariosOnline() {
        this.usuariosOnline = Math.floor(Math.random() * 101); // entra 0 e 100
      }
    },
    created() {
      setInterval(this.getUsuariosOnline, 1000) //declarar this.getUsuariosOnline() com o parêntese irá passar o resultado da funçao. Sem o parêntese indica que é pra executar a função.
      // a cada 1 segundo executar a função.
    },
    //mounted() { //chamado uma única vez quando o componente é montado, gera um problema pois como o keep alive está ligado, quando o componente for reativado , ele não é montado novamente, logo não recarrega atualizacoes, portanto foi substituido pelo activated, que é chamado sempre q o componente for reativado
    activated() { // método chamado sempre q um componente é ativado ou reativado
      this.vagas = JSON.parse(localStorage.getItem('vagas'));
    },
    mounted() { //utilizou o mount e nao o activated, pois o componente esta dentro de um keep alive, entao mesmo quando ele for desativado, na primeira montagem o componente ja tera sido configurado como escutador do evento, e esssa escuta continuara funcionando
      this.emitter.on('filtrarVagas', vaga => {
        //console.log('Estamos no componente Home', vaga);

        const vagas = JSON.parse(localStorage.getItem('vagas'));

        //console.log(vagas);
        this.vagas = vagas.filter(reg => reg.titulo.toLowerCase().includes(vaga.titulo.toLowerCase())); //Cria um novo array com todos os elementos que atenderem a uma condicao
      });
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
