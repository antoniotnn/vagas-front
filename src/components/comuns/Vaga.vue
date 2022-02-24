<template>
    <div class="card">
        <div class="card-header bg-dark text-white">
            <div class="row">
                <div class="col d-flex justify-content-between">
                    <div>
                        {{ titulo }}
                    </div>
                    <div>
                        <div class="form-check form-switch">
                            <input class="form-check-input" type="checkbox" v-model="favoritada">
                            <label class="form-check-label">Favoritar</label>
                            <!--<button class="btn btn-danger" @click="dispararEventoComMitt()">Teste</button>-->
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="card-body">
            <p>{{ descricao }}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">Salário: R$ {{ salario }} | Modalidade: {{ getModalidade }} | Tipo: {{ getTipo }} | Publicação: {{ getPublicacao }}</small>
        </div>
    </div>
</template>

<script>

export default {
    name: 'Vaga',
    data: () => ({
        favoritada: false
    }),
    watch: {
        favoritada(valorNovo) { // aceita 2 parametros, valorNovo, ValorAntigo
            //console.log(valorNovo);
            if(valorNovo) {
                this.emitter.emit('favoritarVaga', this.titulo);
            } else {
                this.emitter.emit('desfavoritarVaga', this.titulo);
            }
        } 
    },
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
    computed: {
        getModalidade() {
            switch(this.modalidade) {
                case '1': return 'Home Office';
                case '2': return 'Presencial';
            }
            return '';
        },
        getTipo() {
            switch(this.tipo) {
                case '1': return 'CLT';
                case '2': return 'PJ';
            }
            return '';
        },
        getPublicacao() {
            let dataPublicacao = new Date(this.publicacao);
            //return dataPublicacao.toLocaleString('pt-BR');
            return dataPublicacao.toLocaleDateString('pt-BR');
        }
    },
    methods: {
        /*
        dispararEventoComMitt() {
            this.emitter.emit('eventoGlobal1', 'Teste Captura Evento Parâmetro'); //2 param: Nome do Evento, Parâmetro enviado para o evento, array, string obj etc (parametro opcional)
        }
        */
    }
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
