<template>  
<div class="container">
  <h1 ref="typewriter">{{ text }}</h1>
</div>
<div class="calculator">
  <div class="display">{{ display }}</div>
  <div class="buttons">
    <button v-for="button in buttons" :key="button" @click="afficher(button)">{{ button }}</button>
    <button @click="Clear">C</button>
    <button @click="Delete">DEL</button>
    <button @click="Review">STORIES</button>
  </div>
</div>
  
</template>

<script>
export default {
  data() {
    return{
      text: 'CALCULATOOOR MITAAPPYYY',
      display: '',
      buttons : ['0','1','2','+','3','4','5','-','6','8','9','/','*','(',')','%','='],
      history : [],
      currentIndex: 0,
      isDeleting: false
    }
  },
  methods: {
    afficher(button){
      if (button === '='){
        let result = eval(this.display)
        this.history.push(`${this.display} = ${result}`)
        this.display = result.toString();
      }else {
        this.display+=button
      }
    },
    Clear() {
      this.display = ''
    },
    Delete() {
      this.display = this.display.slice(0,-1)
    },
    Review() {
      this.display = this.history.join('\n')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  body{
    font-family: 'Courier New', Courier, monospace;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
  }
  h1 {
    text-align:center;
  }
  .calculator {
    width: 350px;
    position: relative;
    height: auto;
    top: -15px;
    margin-left: 34.2%;
    background-color: transparent;
    backdrop-filter: blur(20px);
    border-radius: 10px;
    box-shadow: 0 0 5px black, 0 0 15px blue, 0 0 15px aquamarine;
    padding: 20px;
    // display: flex;
    // flex-direction: column;
    // align-items: center;
    // justify-content: space-between;
  }
  .display {
    background-color: rgba(128, 128, 128, 0.493);
    color: rgb(252, 250, 250);
    font-size: 2em;
    text-align: right;
    padding: 10px;
    border-radius: 20px;
    margin-bottom: 10px;
  }
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 3fr);
    gap: 10px;
    align-items: baseline;
    align-content: stretch;
    justify-items: stretch;
    justify-content: space-evenly;
    
    button{
      padding: 20px;
      font-size: 1.2em;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      background: linear-gradient(0 0 5px blue, 0 1px 15px violet, 0 0 20px aquamarine);

      &:hover{
        background-color: rgba(128, 128, 128, 0.281);
      }

      &:active{
        background-color: #ccc;
      }

      &:nth-child(17){
        background-color: aqua;
        color: black;
      }

      &:nth-child(18){
        background-color: aqua;
        color: black;
      }
      &:nth-child(19){
        background-color: rgba(238, 9, 226, 0.493);
        color: black;
      }
      &:nth-child(20){
        background-color: aqua;
        color: black;
      }

    }
  }


</style>
