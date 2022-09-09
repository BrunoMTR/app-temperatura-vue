<template>
  <div id="root">
    <main class="base">
 
        <BarraPesquisa @buscarTemperatura="buscar"></BarraPesquisa>
        
        <div class="informacao" >
          <Cartao :localizacao="localizacao" :maximo="maximo" :minimo="minimo" :imagem="imagem"> ></Cartao>
          </div>

      

    </main>





  </div> 
</template>

<script>
import BarraPesquisa from './components/BarraPesquisa.vue';
import Cartao from './components/cartao.vue';
import sol from '../src/assets/sun.png';
import nuvem from '../src/assets/storm.png';
export default {
  name: 'App',
  components: { BarraPesquisa ,Cartao },
  data(){
    return{
      chave: 'cf306a304cd8b583d0f969ca38e30891',
      url: 'https://api.openweathermap.org/data/2.5/',
      localizacao: '',
      maximo: null,
      minimo: null,
      imagem: ''
    }
  },
  methods:{
    buscar(busca){
      fetch(`${this.url}weather?q=${busca}&units=metric&APPID=${this.chave}`)
      .then((resposta) => {return resposta.json()})
      .then((dados)=>{ this.localizacao = dados.name; this.maximo= dados.main.temp_max, this.minimo=dados.main.temp_min;
        if(this.maximo >25){
          this.imagem = sol
        }else{
          this.imagem = nuvem
        }
     })
    },
    setup() {
    return {
        sol
    };
},
setup2() {
    return {
        nuvem
    };
}
// ,
// temperaturaAleatoria(){
//     setInterval(()=>{
//       console.log('aqui ')
//     },50000)
//   }
  
  
    
    // fetch(`${this.url}weather?q=${this.provincia[0]}&units=metric&APPID=${this.chave}`)
    //   .then((resposta) => {return resposta.json()})
    //   .then((dados)=>{ this.localizacao = dados.name; this.maximo= dados.main.temp_max, this.minimo=dados.main.temp_min;
    //     if(this.maximo >25){
    //       this.imagem = sol
    //     }else{
    //       this.imagem = nuvem
    //     }
    //  })
    
  }
  // mounted () {
  // this.temperaturaAleatoria()
  //       }
 
}



</script>

<style>
#app {
  font-family: 'montserrat', Helvetica, Arial, sans-serif;
  
 
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
