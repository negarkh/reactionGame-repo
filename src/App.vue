<template>
  <h1>Reaction Timer Game</h1>
  <h3>Click The Play Button To Start The Game</h3>
  <p>Once the Green Box appears,click on it quickly!</p>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" v-bind:delay="delay" @end="endGame"/>
  <Results v-if="showResults" :scoreResult="score" />
</template>

<script>
import Block from './components/Block.vue'

import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results },

  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },

  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionScore){
      this.score = reactionScore
      this.isPlaying = false
      this.showResults = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}

button {
  background: purple;
  color: white;
  border: none;
  padding: 10px 60px;
  border-radius: 4px;
  font-size: 20px;
  margin: 10px;
}
button:disabled {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
