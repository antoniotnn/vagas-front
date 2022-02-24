<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
      <a class="navbar-brand" href="#">Vagas</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <!--<a class="nav-link" href="#" @click="navegarPara()">Home</a>-->
            <!--<a class="nav-link" href="#" @click="funcaoCallback('Teste 1', 200)">Home</a>-->
            <a class="nav-link" href="#" @click="navegarPara('Home')">Home</a>
          </li>
          <li class="nav-item">
            <!--<a class="nav-link" href="#" @click="navegarPara()">Publicar Vaga</a>-->
            <!--<a class="nav-link" href="#" @click="funcaoCallback('Teste 2', 300)">Publicar Vaga</a>-->
            <a class="nav-link" href="#" @click="navegarPara('PublicarVaga')">Publicar Vaga</a>
          </li>
        </ul>
      </div>
    </div>
</nav>
</template>

<script>
  export default {
    name: 'TopoPadrao',
    methods: {
      navegarPara(p) {
        this.$emit('navegar', p)
      }
    }


    /*
    props: {
      funcaoCallback: Function // Definindo a prop funcaoCallback, tipada como Function
    },
    */
    
    /*methods: {
      navegarPara() {
        //console.log('Chegamos até aqui');

        //this.$emit('nomeDoEventoQueSeraCapturadoNoComponentePai'); //emite um evento pro componente pai desse, ou seja quem está fazendo a instância dele.
        // aceita um segundo parametro; um payload, uma funcao de callback, string, array.. etc..
        /*
        this.$emit(//emite um evento pro componente pai desse, ou seja quem está fazendo a instância dele.
          'nomeDoEventoQueSeraCapturadoNoComponentePai',
          { msg: 'Dando um oi para o componente PAI' }
        ); 
        
        this.$emit(//emite um evento pro componente pai desse, ou seja quem está fazendo a instância dele.
          'nomeDoEventoQueSeraCapturadoNoComponentePai',
          (p1, p2) => { 
            console.log('Função de callback emitida pelo componente fiho'); 
            console.log('p1: ', p1);
            console.log('p2: ', p2);
          }
        );
      }
    }*/
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style></style>
