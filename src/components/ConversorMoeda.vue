<template>
  <div class="conversorMoeda">
    <h2> {{ moedaA }} para {{ moedaB }} </h2>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
    <input type="button" value="Conveter" v-on:click="converter">
    <h2> R$ {{ moedaB_value }}  {{ moedaB }} </h2>
  </div>
</template>

<script>

export default {
  name: "ConversorMoeda",
  props: ["moedaA", "moedaB"],

  data(){
    return{
      moedaA_value: "",
      moedaB_value: 0
    };
  },

  methods: {
    converter() {
      let dePara = this.moedaA + "-" + this.moedaB;
      let navJson = this.moedaA+this.moedaB;
      let url = "http://economia.awesomeapi.com.br/json/last/"+ dePara;
      console.log(url)      
    
      fetch(url)
        .then(res => {
          return res.json();
        })
        .then(json => {
          let cotacao = json[navJson].high;
          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value))
        })
    }    
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

.conversorMoeda{
  margin-left: 30px;
  border: 2px solid black;
  border-radius: 10%;
  -webkit-box-shadow: 13px 14px 23px 0px rgba(0,0,0,0.61);
  -moz-box-shadow: 13px 14px 23px 0px rgba(0,0,0,0.61);
  box-shadow: 13px 14px 23px 0px rgba(0,0,0,0.61);
}

</style>
