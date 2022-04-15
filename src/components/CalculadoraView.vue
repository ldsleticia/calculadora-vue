<template>
  <div class="aprender-bg">
    <div class="aprender-bg-2">
      <div class="aprender-bg-3">
        <p class="texto-cinza-700">{{ getOperation }}</p>
        <p class="texto-cinza-900">{{ getResult }}</p>
      </div>

      <div class="botoes">
        <button class="ac" @click="handleClickAC()">AC</button>
        <button @click="handleClickDel()">DEL</button>
        <button @click="handleClick('/')">/</button>

        <button @click="handleClick('7')">7</button>
        <button @click="handleClick('8')">8</button>
        <button @click="handleClick('9')">9</button>
        <button @click="handleClick('x')">X</button>

        <button @click="handleClick('4')">4</button>
        <button @click="handleClick('5')">5</button>
        <button @click="handleClick('6')">6</button>
        <button @click="handleClick('-')">-</button>

        <button @click="handleClick('3')">3</button>
        <button @click="handleClick('2')">2</button>
        <button @click="handleClick('1')">1</button>
        <button @click="handleClick('-')">+</button>

        <button @click="handleClick('0')">0</button>
        <button @click="handleClick('.')">.</button>
        <button @click="handleClickResult()">=</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      getOperation: "",
      getResult: "0",
    };
  },
  methods: {
    handleClickAC() {
      this.getResult = "0";
    },
    handleClick(par) {
      if (this.getResult === "0") {
        this.getResult = par;
      } else {
        this.getResult += par;
      }
    },
    handleClickDel() {
      if (this.getResult.length > 1) {
        this.getResult = this.getResult.substring(0, this.getResult.length - 1);
      } else {
          this.getResult = '0'
      }
    },
    handleClickResult() {
        let operation = this.getResult
        this.getOperation = operation
        operation = operation.replace('x', '*')
        this.getResult = eval(operation)
    }
  },
};
</script>