<template>
  <div class="calculator">
    <input type="text" v-model="expression" class="expression-input" readonly>
    <div class="buttons">
      <button v-for="button in buttons" :key="button" @click="handleButtonClick(button)">
        {{ button }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalCulator',
  data() {
    return {
      expression: '',
      buttons: ['7', '8', '9', '+', '4', '5', '6', '-', '1', '2', '3', '*', '0', '.', '=', '/','(',')','DEL', 'C'],
    };
  },
  methods: {
    handleButtonClick(button) {
      if (button === '=') {
        this.calculate();
      }
      else if (button === 'ON') {
        this.expression = '0';
      }
      else if (button === 'C') {
        this.expression = '';
      }
      else if (button === 'DEL'){
        this.expression = this.expression.substring(0, this.expression.length - 1);
      }
      
      else {
        this.expression += button;
      }
    },
   

    calculate() {
      try {
        this.expression = eval(this.expression);
      } catch (error) {
        this.expression = 'Error';
      }
    },
    
  },
};
</script>

<style scoped>


.calculator {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color:  #8AAAE5;
}

.expression-input {
  width: 100%;
  margin-bottom: 10px;
  padding: 10px;
  font-size: 18px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
  /* background-color: white; */
}

button {
  padding: 10px;
  font-size: 16px;
  background-color: rgb(248, 243, 243); 
  border: 2px solid #b0adad;
}
button:hover {
  
  background-color: rgb(5, 5, 5); 
  color: white;
  border: 2px solid #b0adad;
  box-shadow: 5px 2px 2px  grey;
}
/* make a transation when user clicked on button */
button:active {
  transform: scale(0.98);
}
/* align clear button center */


  


  




</style>
