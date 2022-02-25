<template>
    <div>
        <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
            <div class="col">
                <vaga v-bind="vaga"/>
            </div>
        </div>
    </div>
</template>

<script>
import Vaga from '@/components/comuns/Vaga.vue';

export default {
    name: 'ListaVagas',
    props: {
        vagas: Array
    },
    components: {
        Vaga
    }
}
</script>
