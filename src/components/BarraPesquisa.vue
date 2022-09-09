<template>

<div class="bloco-pesquisa">
    <input type="text" class="barra-pesquisa" placeholder="pesquise..." v-model="busca">
    <button class="botao-pesquisar" @click="fetchTemperatura">Pesquisar</button>

</div>



</template>

<script>
export default{
    name: 'BarraPesquisa',
    data(){
        return{
            busca: '',
            temperatura:[]
        }
    },
    methods:{
        fetchTemperatura(){

            this.$emit('buscarTemperatura',this.busca);
        }
}
}


</script>

<style>
    .barra-pesquisa{
        padding: 10px;
        width: 80%;
        appearance: none;
        border:none;
        outline: none;
        background: none;
        
    }
    .botao-pesquisar{
        padding: 10px;
        background-color: #411530;
        color: white;
        margin-left: 5x;
        border:none;
        outline: none;
      
    }
    .bloco-pesquisa{
        display: flex;
        justify-content: space-between
        ;
        background-color: white;
        width: 40%;
        padding: 2px;
        margin-top: 50px;
        margin-left: 24%;
        border-radius: 5px;
    }



</style>