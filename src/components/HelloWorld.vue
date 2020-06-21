<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <hr>

    <h2>Sumadora Simple</h2>
    <br>

    <form>
      <input type="text" class="field" v-model="numero1"  maxlength="2" />
      <span> + </span>
      <input type="text" class="field" v-model="numero2"  maxlength="2" />
      <span> = </span>
      <span class="field">{{resultado}}</span>

    </form>



  
  
  </div>
</template>

<script>

import { reactive, computed, toRefs } from "vue"


function usarCalculadora(){

   let state = reactive({
      numero1:0,
      numero2:0,
      resultado: computed(() =>{
        return state.resultado = parseInt(state.numero1) + parseInt(state.numero2);
      })
    })

    return toRefs(state);

}

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  setup(){

   let { numero1, numero2, resultado } = usarCalculadora();

    return {
      numero1,numero2,resultado
      
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
