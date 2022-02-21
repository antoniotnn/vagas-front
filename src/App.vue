<template>
  <div>
    <h1>Componente App</h1>
    <topo-padrao />
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
