<template>
    <slot :vagas="vagas">
        <div>
            <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
                <div class="col">
                    <vaga v-bind="vaga"/>
                </div>
            </div>
        </div>
    </slot>
</template>

<script>
import Vaga from '@/components/comuns/Vaga.vue';

export default {
    name: 'ListaVagas',
    data: () => ({
        vagas: []
    }),
    components: {
        Vaga
    },
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
