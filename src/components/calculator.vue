<template>
  <div class="app">
    <div class="calculator">
      <input  @keyup.enter="calc" type="text" placeholder="0" v-model="result" >
        <div>
          <div class="left">
            <div class="numbers">
              <button  @click="input(num)" class="cell num" v-for="num in numbers" :key="num">{{num}}</button>
              <button  @click="reset" class="cell op">R</button>
              <button  @click="calc" class="cell op">=</button>
            </div>
            <div class="operations">
              <button  @click="input(op)" class="cell op" v-for="op in operations" :key="op">{{op}}</button>
            </div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'HelloWorld',
data() {
    return {
      result: "",
      numbers: [1,2,3,4,5,6,7,8,9,0],
      operations: ['+','-','*','/'],
      status: false,
      type: Number
      }
    },
  methods: {
  input(char) {
    if (!this.status) {
      this.status = true
      this.result = ''
      if (char.typeof == this.type)
      this.result = this.result.toString()
      this.result+=char
    } else {
      if (char.typeof == this.type)
      this.result = this.result.toString()
      this.result+=char
    }
  },
    reset() {
      this.result = '';
    },
    calc() {
      this.result = eval(this.result);
      this.status = !this.status
    }
  },
}


</script>
