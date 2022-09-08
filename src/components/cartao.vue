<template>
<div class="cartao">
<h2 class="lugar">{{localizacao}}</h2>
<img src={{imagem}} alt="imagem" class="imagem">


<div class="temperatura">
    <h3>{{maximo}}</h3>
<h3>{{minimo}}</h3>

</div>

</div>



</template>



<script>
export default{
    name: 'Cartao-meteorico',
    props:{
        localizacao: {
                type: String,
                required: false
            },
            imagem: {
                type: Image,
                required: false
            },
            maximo: {
                type: String,
                required: false
            },
            minimo: {
                type: String,
                required: false
            }
    }


}
    
</script>


<style>
.cartao{
    background-color: #4E3863;
    width: 300px;
    height: 350px;
    color: white;
    border-radius: 5px;
    margin-right: 10px;
   
}
.lugar{
    text-align: center;
    
}
.imagem{

    margin-left: 30%;
    
    
}

.temperatura{
    margin-top: 30%;
    display: flex;
    justify-content: space-around;
}



</style>
