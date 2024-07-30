<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" placeholder="Valor em Dólar:">
        <input type="button" value="Converter" v-on:click="converterUSD_BRL">
        <h2>{{resultUSD_BRL}}</h2>
    </div>

    <div class="conversor">
        <h2>{{moedaB}} Para {{moedaA}}</h2>
        <input type="text" v-model="moedaB_value" placeholder="Valor em Real:">
        <input type="button" value="Converter" v-on:click="converterBRL_USD">
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
            resultUSD_BRL: 0,
            resultBRL_USD: 0
        }
    },

    methods:{
        converterUSD_BRL(){
            this.resultUSD_BRL = (this.moedaA_value * 5.6161006159).toFixed(2) + " Reais";
            return this.resultUSD_BRL;
        },
        converterBRL_USD(){
            this.resultBRL_USD = (this.moedaB_value * 0.178059488).toFixed(2) + " Dolares";
            return this.resultBRL_USD;
            
        }
    }
};
</script>

<style>

.conversor{
    margin: 20px;
    padding: 50px;
    padding-left: 215px;
    padding-right: 215px;
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
</style>