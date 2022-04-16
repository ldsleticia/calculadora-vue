<template>
  <div class="h-screen bg-green-400 flex justify-center py-16">
    <div class="w-1/3">
      <div class="p-4 text-right shadow-2x1 rounded-t-lg bg-white">
        <p class="font-semibold text-gray-700 h-6"> {{ getOperation }} </p>
        <p class="font-bold text-3xl text-gray-900 my-2"> {{ getResult }} </p>
      </div>

      <div class="grid grid-cols-4 grid-rows-5 shadow-2x1 rounded-b-lg">

        <button class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 col-span-2 hover:bg-green-600" @click="handleClickAC()">AC</button>

        <button class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClickDel()">DEL</button>

        <button class="h-16 text-xl text-white font-semibold bg-gray-700 border-gray-600 hover:bg-gray-800" @click="handleClick('÷')">÷</button>

        <button class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('7')">7</button>
        
        <button class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('8')">8</button>

        <button class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('9')">9</button>

        <button class="h-16 text-xl text-white font-semibold bg-gray-700 border-gray-600 hover:bg-gray-800" @click="handleClick('x')">X</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('4')">4</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('5')">5</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('6')">6</button>

        <button  class="h-16 text-xl text-white font-semibold bg-gray-700 border-gray-600 hover:bg-gray-800" @click="handleClick('-')">-</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('3')">3</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('2')">2</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('1')">1</button>

        <button  class="h-16 text-xl text-white font-semibold bg-gray-700 border-gray-600 hover:bg-gray-800" @click="handleClick('+')">+</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 col-span-2 hover:bg-green-600" @click="handleClick('0')">0</button>

        <button  class="h-16 text-xl text-white font-semibold bg-green-500 border-green-400 hover:bg-green-600" @click="handleClick('.')">.</button>

        <button  class="h-16 text-xl text-white font-semibold bg-gray-700 border-gray-600 hover:bg-gray-800" @click="handleClickResult()">=</button>

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
  computed: {
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

<style scoped>

button {
  border: 1px solid;
}
</style>