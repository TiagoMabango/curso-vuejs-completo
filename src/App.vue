<template>
  <div id="app">

    <h1>Bem Vindo ao meu primeiro projecto</h1>
      <button @click="entrar"> entrar</button>
    <Usuario :nome="nome"/>
  </div>
</template>

<script>

import Usuario from "./components/Usuario.vue"


export default {  
  name: 'App',
  components:{
    Usuario
  },
  data(){
    return{
      nome: 'Sujeito Programador'
    }
  },
  methods:{
    entrar(){
      this.nome = 'Tiago Mabango'
    }
  }
}
</script>

<style >

</style>