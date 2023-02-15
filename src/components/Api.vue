<script>
export default {
  data() {
    return {
      myArray: ['one', 'two', 'three', 'four', 'five'],
      randomItem: ''
    }
  },
  /*methods: {
    chooseRandomItem() {
    	let randomElement = Math.floor(Math.random() * this.myArray.length);
    	this.randomItem = this.myArray[randomElement]; 
    }
  },*/
  mounted(){
  	let randomElement = Math.floor(Math.random() * this.myArray.length);
    this.randomItem = this.myArray[randomElement];
  }
}
</script>

<template>
  <p>value: {{ randomItem }}</p>

  <!-- <button @click="chooseRandomItem">click</button> -->
</template>

<style>
	
</style>