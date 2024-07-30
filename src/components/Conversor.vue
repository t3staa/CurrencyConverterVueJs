<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" placeholder="Valor em USD:">
        <input type="button" value="Converter" v-on:click="converterUSD_BRL">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
export default {
    name: "ConversorComponetUSD_BRL",
    props: ["moedaA", "moedaB"],
    data(){
        return{
            moedaA_value : "",
            moedaB_value : 0
        }
    },

    methods:{
        converterUSD_BRL(){
            this.moedaB_value = (this.moedaA_value * 5.6161006159).toFixed(2) + " R$";
            return this.moedaB_value;
        }
    }
};
</script>

<style scoped>
.conversor{
   padding: 20px;
   max-width: 300px; 
   box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}
</style>