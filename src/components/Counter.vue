<template>
  <h2>{{ title }}</h2>
  <p>{{ counter }} <sup>2</sup> = {{squareCounter}}</p>

  <div>
    <button @click="getDecrease()">-1</button>
    <button @click="getIncrease()">+1</button>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Contador'
    },
    start: {
      type: Number,
      default: 100,
      validator(value) {
        return value >= 2
      }
    }
  },
  name: 'Counter',
  data() {
    return {
      counter: this.start
    }
  },
  methods: {
    getSquareValue() {
      console.log('getSquareValue')
      return this.counter * this.counter
    },
    getIncrease() {
      return this.counter++
    },
    getDecrease() {
      return this.counter--
    }
  },
  computed: {
    squareCounter() {
      console.log('computed squareCounter')
      return this.counter * this.counter
    }
  }
}
</script>

<style>
button {
  background-color: #64BB87;
  border-radius: 5px;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}
</style>