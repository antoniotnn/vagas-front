<template>
  <div>
    <h1>Componente Conteúdo</h1>
    <home></home>
    <publicar-vaga></publicar-vaga>
  </div>
</template>

<script>
import Home from '@/components/views/Home.vue'
import PublicarVaga from '@/components/views/PublicarVaga.vue'
  export default {
    name: 'Conteudo',
    components: {
      Home,
      PublicarVaga
    },
    methods: {

    },
    beforeCreate() {
      console.log('Antes de criar');
    },
    created() {
      console.log('Criado');
    },
    beforeMount() {
      console.log('Antes de montar')
    },
    mounted() {
      console.log('Montado')
    },
    beforeUpdate() {
      console.log('Antes de atualizar')
    },
    updated() {
      console.log('Atualizado')
    },
    beforeUnmount() {
      console.log('Antes de desmontar/destruir')
    },
    unmounted() {
      console.log('Desmontado/destruído')
    },
    errorCaptured() {
      console.log('Erro capturado')
    },
    renderTracked() {
      console.log('Re-renderização rastreada')
    },
    renderTriggered() {
      console.log('Re-renderização ativada')
    },
    activated() {
      console.log('Componente ativado')
    },
    deActivated() {
      console.log('Componente desativado')
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
