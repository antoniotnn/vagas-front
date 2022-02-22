<template>
    <div class="card">
        <div class="card-header bg-dark text-white">{{ titulo }}</div>
        <div class="card-body">
            <p>{{ descricao }}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">Salário: R$ {{ salario }} | Modalidade: {{ modalidade }} | Tipo: {{ tipo }} | Publicação: {{ publicacao }}</small>
        </div>
    </div>
</template>

<script>

export default {
    name: 'Vaga',
    //props: ['tituloVagaTeste', 'descricaoVaga', 'salario', 'modalidade', 'tipo', 'publicacao'],
    //tipagens: String, Number, Boolean, Array, Object, Date, Function, Symbol
    props: {
        titulo: {
            type: String,
            required: true,
            validator(p) {
                //console.log('Prop: ', p, p.length);
                if(p.length < 6) return false; //se estiver inválido
                return true; //se estiver válido
            }
        },
        descricao: {
            type: String,
            //required: true,
            //default: 'O contratante não adicionou uma descrição para esta vaga'
            default() {
                return '*'.repeat(20);
            }
        },
        salario: {
            type: [Number, String],
            required: true
        },
        modalidade: {
            type: String,
            required: true
        },
        tipo: {
            type: String,
            required: true
        },
        publicacao: {
            type: String,
            required: true
        }
    },
    /*
    created () {
        console.log('tituloVagaTeste', typeof this.tituloVagaTeste);
        console.log('descricaoVaga', typeof this.descricaoVaga);
        console.log('salario', typeof this.salario);
        console.log('modalidade', typeof this.modalidade);
        console.log('tipo', typeof this.tipo);
        console.log('publicacao', typeof this.publicacao);
    }*/
}
</script>
