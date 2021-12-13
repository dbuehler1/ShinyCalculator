<template>
  <div id="app">
    <div class="border border-dark rounded p-2 bg-secondary">
      <h2 class="bg-info p-2 border border-dark">Shiny Calculator</h2>
      <h3>Your Number: 1576</h3>
      <h5>Number of Guesses: {{this.counter}}</h5>
      <ShinyNumList
          :shiny-collection="numbers"
          :test-num="this.testNum"
      ></ShinyNumList><br>
      <button class="btn btn-success float-right" @click="calcShiny">Find Shiny</button><br><br>
    </div>

  </div>
</template>

<script>
import ShinyNumList from "@/components/ShinyNumList";

export default {
  name: 'App',
  data() {
    return {
      numbers : [],
      counter : 0,
      testNum : 0,
    }
  },
  components: {
    ShinyNumList

  },
  methods : {
    calcShiny() {
      var testnum = 0;
      var originalNum = 1576;
      this.counter = 0;

      this.numbers.splice(0);
      do {
        testnum = Math.floor(Math.random() * 8192) + 1;
        //8192
        this.numbers.push(testnum);
        this.counter++;
      } while (testnum !== originalNum);
      this.testNum = testnum;

    }
  }
}
</script>

<style>
#app {
  /*font-family: Avenir, Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
  margin-right: auto;
  margin-left: auto;
  width: 20rem;
  text-align: center;
  padding: 1rem;
}
</style>
