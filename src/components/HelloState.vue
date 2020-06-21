<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <hr>

    <h2>Sumadora Simple</h2>
    <br>

    <form>
      <input type="text" class="field" v-model="state.numero1" @keyup="sumarNumeros" maxlength="2" />
      <span> + </span>
      <input type="text" class="field" v-model="state.numero2" @keyup="sumarNumeros" maxlength="2" />
      <span> = </span>
      <span class="field">{{state.resultado}}</span>

    </form>



  
  
  </div>
</template>

<script>

import { reactive } from "vue"

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  setup(){

    let state = reactive({
      numero1:0,
      numero2:0,
      resultado:0
    })


    function sumarNumeros(){
      state.resultado = parseInt(state.numero1) + parseInt(state.numero2);
    }


    return {
      state,
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
