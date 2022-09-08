<template>
  <div id="root">
    <main class="base">
 
        <BarraPesquisa @buscarTemperatura="buscar"></BarraPesquisa>
        
        <div class="informacao" v-if="typeof temperatura.name != 'undefined'">

          <Cartao></Cartao>
          {{temperatura.name}}
          <Cartao></Cartao>
          <Cartao></Cartao>

        </div>

      

    </main>





  </div> 
</template>

<script>
import BarraPesquisa from './components/BarraPesquisa.vue';
import Cartao from './components/cartao.vue';
export default {
  name: 'App',
  components: { BarraPesquisa ,Cartao },
  data(){
    return{
      chave: 'cf306a304cd8b583d0f969ca38e30891',
      url: 'https://api.openweathermap.org/data/2.5/',
      temperatura: {}
    }
  },
  methods:{
    buscar(busca){
      fetch(`${this.url}weather?q=${busca}&units=metric&APPID=${this.chave}`)
          .then(res => {
            return res.json();
          }).then(this.setResults);
    },
    Resultado (resultados) {
      this.temperatura = resultados;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
 
}

.base{
  width: 100vw;
  height: 100vh;
  background: linear-gradient(150deg, #411530 60%, white 40%);
  display: flex;
  flex-direction: column;
}

.informacao{
  display: flex;
  justify-content: center;
  padding: 5px;
  margin-top: 10%;
  }

</style>
