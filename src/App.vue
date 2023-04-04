<template>

    <div id="app">
          <img  class="img" alt="Vue logo" src="./assets/cronometro.png">
          <a class="timer"> {{numero}} </a>

          <div class="areaBtn">
              <button class="botao" @click="vai"> {{botao}}</button>
              <button class="botao" @click="limpar">LIMPAR</button>
          </div>
    </div>
  
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      numero:0,
      botao: 'VAI',
      timer: null,
      ss: 0,
      mm: 0,
      hh:0
    }
  },
  methods:{
    vai(){
      if(this.timer !== null){
        clearInterval(this.timer)
        this.timer = null
        this.botao = 'VAI'
      }else{
        this.timer = setInterval(()=>{
          this.rodarTimer()
        }, 100)
          this.botao = 'PAUSAR'
      }

      
      
    },
    limpar(){

    },
    rodarTimer(){
      this.ss++

      if(this.ss == 59){
        this.ss = 0
        this.mm++
      }

      if(this.mm == 59) {
        this.mm = 0
        this.hh++
      }

      let format = (this.hh < 10 ? '0'+ this.hh: this.hh) + ':'
      + (this.mm <10 ? '0'+this.mm : this.mm) + ',' 
      +(this.ss < 10 ?  '0'+this.ss : this.ss)

      return this.numero = format
     }
  }
}
</script>

<style>
#app {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.img{
  width: 420px;
  height: 420px;
  padding-top: 100px;
}

.timer{
  color: #fff;
  font-size: 70px;
  margin-top: -210px;
}

.areaBtn{
  margin-top: 155px;
  display: flex;
}

.botao{
  -webkit-user-select: none;
  width: 150px;
  background-color:#fff ;
  font-size: 20px;
  border: 0;
  border-radius: 5px;
  text-align: center;
  margin-left: 15px;
  margin-right: 15px;
  padding: 6px;
  cursor: pointer;
}

.botao:hover{
  opacity: 0.7;
  transition: all 0.50s;
}
</style>
