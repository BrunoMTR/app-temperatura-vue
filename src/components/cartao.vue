<template>
<div class="cartao">
<h2 class="lugar">{{localizacao}}</h2>
<img :src= imagem alt="imagem" class="imagem">


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
                type: String,
                required: false
            },
            maximo: {
                type: Number,
                required: false
            },
            minimo: {
                type: Number,
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
    margin-right: 10px;

    /* From https://css.glass */
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.3);


   
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
