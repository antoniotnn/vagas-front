<template>
  <div>
    <h1>Componente Home</h1>
  </div>
</template>

<script>
  export default {
    name: 'Home',
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
