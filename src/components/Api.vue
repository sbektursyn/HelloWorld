<script>
  import axios from 'axios'
export default {
  data() {
    return {
      myArray: ['one', 'two', 'three', 'four', 'five'],
      randomItem: '',
      info: null,
      value: null
    }
  },
  methods: {
    /*chooseRandomItem() {
    	let randomElement = Math.floor(Math.random() * this.myArray.length);
    	this.randomItem = this.myArray[randomElement]; 
    }*/
    getValue(){
      axios
        .get('https://api.chucknorris.io/jokes/random')
        .then(response => (this.value = response.data.value));

    }
  },
  mounted(){
  	let randomElement = Math.floor(Math.random() * this.myArray.length);
    this.randomItem = this.myArray[randomElement];
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(some => (this.info = some));
    
  }
}
</script>

<template>
  <!-- <p>value: {{ randomItem }}</p> -->
  {{info.data.chartName}}
  <ul>
    <li>
      USD = {{info.data.bpi.USD.rate}}$
    </li>
    <li>
      GBP = {{info.data.bpi.GBP.rate}}
    </li>
    <li>
      EUR = {{info.data.bpi.EUR.rate}}
    </li>
  </ul>

  

  value: {{value}}

  <br>
  <button @click="getValue">OOO</button>

  <!-- <button @click="chooseRandomItem">click</button> -->
</template>

<style>

</style>