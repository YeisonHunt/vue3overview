<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <hr>

    <h2>Sumadora Simple</h2>
    <br>

    <form>
      <input type="text" class="field" v-model="numero1" @keyup="sumarNumeros" maxlength="2" />
      <span> + </span>
      <input type="text" class="field" v-model="numero2" @keyup="sumarNumeros" maxlength="2" />
      <span> = </span>
      <span class="field">{{resultado}}</span>

    </form>



  
  
  </div>
</template>

<script>

import { ref } from "vue"

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  setup(){

    let numero1 = ref(0);
    let numero2 = ref(0);
    let resultado = ref(0);


    function sumarNumeros(){
      resultado.value = parseInt(numero1.value) + parseInt(numero2.value);
    }


    return {
      numero1,
      numero2,
      resultado,
      sumarNumeros
    }


  }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .field {
    padding:10px;
    border-radius:5px;
  }
</style>
