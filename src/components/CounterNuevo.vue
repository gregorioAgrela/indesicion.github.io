<template>
  <h2> {{ customeTitle }}</h2>
  <p> {{ counter }} <sub>2</sub> = {{ getSquareValue() }} </p>
  <div>
    <button @click="increase"> +1 </button>
    <button v-on:click="decrease"> -1 </button>
  </div>
</template>
<script>
export default {
  props: {
    title: String,
    start: {
      type: Number,
      required: true,
      default: 100,
      validator (value) {
        return value >= 0
      }
    }
  },
  // name: 'Vue/Multi-Word-Component'
  data () {
    return {
      name: 'ounter',
      counter: parseInt(this.start)
    }
  },
  methods: {
    getSquareValue () {
      return this.counter * this.counter
    },
    increase () {
      this.counter += 1
    },
    decrease () {
      this.counter -= 1
    }
  },
  computed: {
    squareCouinter () {
      return this.counter * this.counter
    },
    customeTitle () {
      return this.title || 'valor por defecto'
    }
  }

}
</script>
<style>
  button {
    background-color: #5aa67b;
    border-radius:5px;
    border: 1px solid white;
    color:white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out
  }
  button:hover {
    background-color: #5aa67b;
    transition: 0.3s ease-in-out
  }
</style>
