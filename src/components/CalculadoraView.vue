<template>
  <div>
    <div>
      <div>
        <p>{{ getOperation }}</p>
        <p >{{ getResult }}</p>
      </div>

      <div class="columns is-3">
        <button @click="handleClickAC()" class="button is-primary column is-3" >AC</button>
        <button @click="handleClickDel()" class="button is-primary column is-2">DEL</button>
        <button @click="handleClick('÷')" class="button is-primary column is-1">÷</button>

        <button @click="handleClick('7')" class="button is-primary column">7</button>
        <button @click="handleClick('8')" class="button is-primary column">8</button>
        <button @click="handleClick('9')" class="button is-primary column">9</button>
        <button @click="handleClick('x')" class="button is-primary column">X</button>

        <button @click="handleClick('4')" class="button is-primary column">4</button>
        <button @click="handleClick('5')" class="button is-primary column">5</button>
        <button @click="handleClick('6')" class="button is-primary column">6</button>
        <button @click="handleClick('-')" class="button is-primary column">-</button>

        <button @click="handleClick('3')" class="button is-primary column">3</button>
        <button @click="handleClick('2')" class="button is-primary column">2</button>
        <button @click="handleClick('1')" class="button is-primary column">1</button>
        <button @click="handleClick('-')" class="button is-primary column">+</button>

        <button @click="handleClick('0')" class="button is-primary column">0</button>
        <button @click="handleClick('.')" class="button is-primary column">.</button>
        <button @click="handleClickResult()" class="button is-primary column">=</button>
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
        operation = operation.replace('÷', '/')
        this.getResult = eval(operation)
    }
  },
};
</script>