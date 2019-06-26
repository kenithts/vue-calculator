<template>

<div class="main">
  <div class="body">
    <div class="grid1">
      <input class="display" type="text" v-model="text_content"/>
    </div>
    <div class="grid2">
       <button v-on:click="ce()" class="operator">CE</button>
       <button v-on:click="add()" class="operator">+</button>
       <button v-on:click="subtract()" class="operator">-</button>
       <button v-on:click="mult()" class="operator">x</button>
       <button v-on:click="divide()" class="operator">/</button>
       <button v-on:click="equal()" class="operator">=</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'calc',

  data: function(){
    return{
      text_content: '0',
      previous: 0,
      operator: ''
    }
  },

  methods:{
    ce: function ce(){
      this.previous = '0'
      this.text_content = '0'
    },
    add: function add(){  
      this.previous = this.text_content;
      this.text_content = ''
      this.operator = '+'
    },
    subtract: function subtract(){  
      this.previous = this.text_content;
      this.text_content = ''
      this.operator = '-'
    },
    mult: function mult(){  
      this.previous = this.text_content;
      this.text_content = ''
      this.operator = 'x'
    },
    divide: function divide(){  
      this.previous = this.text_content;
      this.text_content = ''
      this.operator = '/'
    },
    equal: function equal(){  
      if(this.operator == '+'){
      this.text_content = Number(this.previous) + Number(this.text_content)
      }
      if(this.operator == '-'){
      this.text_content = Number(this.previous) - Number(this.text_content)
      }
      if(this.operator == 'x'){
      this.text_content = Number(this.previous) * Number(this.text_content)
      }
      if(this.operator == '/'){
      this.text_content = Number(this.previous) / Number(this.text_content)
      }
    }
    
  }

}
</script>

<style>

.main{
  display: flex;
  justify-content: center;
}
.body{
  list-style: none;
  display: flex;
  background-color: beige;
  align-content: center;
  justify-content: center;
  flex-direction: column;

  width: 500px;
  height: 250px;
}
.grid1{
  display: flex;
  background-color: rgb(135,203,200);
  justify-content: center;
}

.grid2{
  display: flex;
  background-color: rgb(135,203,200);
  height: 200px;
  justify-content: space-around;
}
.display{
  background-color: white;
  width: 400px;
  height: 100px;
  font-size: 50px;
}

.operator{
  font-size: 50px;
  font-style: bold;
  align-self: center;
  border: 5px solid black;
  flex: 1;
  background-color: rgb(135,203,200);
}
.operator:hover{
  cursor: pointer;
}

</style>
