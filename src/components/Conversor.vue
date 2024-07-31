<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input class="input" type="text" v-model="moedaA_value" placeholder="Valor em Dólar:">
        <input class="btn" type="button" value="Converter" v-on:click="converterUSD_BRL">
        <h2>{{resultUSD_BRL}}</h2>
    </div>

    <div class="conversor">
        <h2>{{moedaB}} Para {{moedaA}}</h2>
        <input class="input" type="text" v-model="moedaB_value" placeholder="Valor em Real:">
        <input class="btn" type="button" value="Converter" v-on:click="converterBRL_USD">
        <h2>{{resultBRL_USD}}</h2>
    </div>
</template>

<script>
export default {
    name: "ConversorComponent",
    props: ["moedaA", "moedaB"],
    data(){
        return{
            moedaA_value: "",
            moedaB_value: "",
            resultUSD_BRL: "Resultado: ",
            resultBRL_USD: "Resultado: "
        }
    },

    methods:{
        converterUSD_BRL(){
            fetch('https://economia.awesomeapi.com.br/last/USD-BRL')
                .then(res=>{return res.json()})
                .then(json=>{
                    let cotacao = json["USDBRL"].bid
                    this.resultUSD_BRL = (cotacao * parseFloat(this.moedaA_value)).toFixed(2) + " Reais";
                }) 
        },
        converterBRL_USD(){
            fetch('https://economia.awesomeapi.com.br/last/BRL-USD')
                .then(res=>{return res.json()})
                .then(json=>{
                    let cotacao = json["BRLUSD"].bid
                    this.resultBRL_USD = (cotacao * parseFloat(this.moedaB_value)).toFixed(2) + " Dólares";
                }) 
        }
    }
};
</script>

<style>
.conversor{
    margin: 20px;
    padding: 50px;
    padding-left: 165px;
    padding-right: 165px;
    max-width: auto; 
    box-shadow: 0 .5rem 1.5rem rgba(0,0,0,.1);
    border-radius: .5rem;
    border: .1rem solid rgba(0,0,0,.1);
    display: inline-block;
    justify-content: space-between;
}

.titulo{
    padding: 10px;
    margin-right: 35px;
    margin-left: 35px;
    max-width: auto;
    box-shadow: 0 .5rem 1.5rem rgba(0,0,0,.1);
    border-radius: .5rem;
    border: .1rem solid rgba(0,0,0,.1);
}

.input{
    margin: 5px;
    padding: 5px;
    border-radius: .2rem;
}

.btn{
    margin: 5px;
    padding: 5px;
    border-radius: .2rem;
}

.btn:hover{
    background-color: rgb(176, 176, 176);
}

@media(max-width: 449px){
    .conversor{
        margin: 5px;
        padding: 20px;
        padding-left: 25px;
        padding-right: 25px;
        max-width: auto; 
    }

    .titulo{
        padding: 5px;
        margin-right: 6px;
        margin-left: 6px;
        max-width: auto;
    }
}

@media (min-width: 450px) and (max-width: 830px){
    .conversor{
        margin: 10px;
        padding: 20px;
        padding-left: 50px;
        padding-right: 50px;
        max-width: auto; 
    }

    .titulo{
        padding: 5px;
        margin-right: 50px;
        margin-left: 50px;
        max-width: auto;
    }
}
</style>