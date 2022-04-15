<template>
  <div class="">
      <div class="sobe">
        <h2>{{ getOperation }}</h2>
        <h1sud >{{ getResult }}</h1sud>
      </div>
    <div class="hero-body ">
      <div class="columns is-3">
        <button @click="handleClickAC()" class="" >AC</button>
        <button @click="handleClickDel()" class="">DEL</button>
        <button @click="handleClick('÷')" class="">÷</button>

        <button @click="handleClick('7')" class="">7</button>
        <button @click="handleClick('8')" class="">8</button>
        <button @click="handleClick('9')" class="">9</button>
        <button @click="handleClick('x')" class="">X</button>

        <button @click="handleClick('4')" class="">4</button>
        <button @click="handleClick('5')" class="">5</button>
        <button @click="handleClick('6')" class="">6</button>
        <button @click="handleClick('-')" class="">-</button>

        <button @click="handleClick('3')" class="">3</button>
        <button @click="handleClick('2')" class="">2</button>
        <button @click="handleClick('1')" class="">1</button>
        <button @click="handleClick('-')" class="">+</button>

        <button @click="handleClick('0')" class="">0</button>
        <button @click="handleClick('.')" class="">.</button>
        <button @click="handleClickResult()" class="">=</button>
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