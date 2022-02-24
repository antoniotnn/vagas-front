<template>
    <div>
        <div class="divVagasFavoritas">
            <button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight" aria-controls="offcanvasRight">Vagas Favoritas</button>
        </div>

        <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">
            <div class="offcanvas-header">
                <h5 id="offcanvasRightLabel">Vagas Favoritadas</h5>
                <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
            </div>
            <div class="offcanvas-body">
                <ul class="list-group">
                    <li class="list-group-item" v-for="(vaga, index) in vagas" :key="index">{{ vaga }}</li>
                </ul>
            </div>
        </div>

    </div>
</template>

<script>
export default {
   name: 'VagasFavoritas',
   data: () => ({
       vagas: []
   }),
   mounted() {
       this.emitter.on('favoritarVaga', (titulo) => {
           //console.log('favoritar: ', titulo);
           this.vagas.push(titulo);
       });

       this.emitter.on('desfavoritarVaga', (titulo) => {
           //console.log('desfavoritar: ', titulo);
           let indiceArray = this.vagas.indexOf(titulo); //retorna -1 se não encontrar a posição do erray com o elemento indicado, se encontrar, retorna o indice do array cmo o elemento
           if(indiceArray !== -1) this.vagas.splice(indiceArray, 1); // remover um elemento a partir de um índice do array. A partir do indice indicado (indiceArray), remover 1 posição, incluindo ele mesmo.. no caso a própria posicao
       });
       /*
       this.emitter.on('eventoGlobal1', (p) => {
           console.log('Componente Vagas Favoritas', p);
       }); // capturando evento. Usa os 2 parametros (nome evento, funcao callback que trata o parametro emitido pelo emissor)
       */
   }
}
</script>

<style scoped>
    .divVagasFavoritas {
        position: absolute; 
        z-index: 1; 
        top: 70px; 
        right: 0px;
    }
</style>
