<template>
  <h2>Let's test your reflection!</h2>
  <button class="btn" :disabled="isPlaying" @click="play">Play</button>
  <PlayBlock v-if="isPlaying" :delay="delay" @end="end" />
  <Score v-if="showScore" :score="score"/>
</template>

<script>
import PlayBlock from './components/PlayBlock.vue'
import Score from './components/ReactionScore.vue'
export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score:null,
      showScore:false,
    }
  },
  components: {
    PlayBlock,Score
  },
  methods: {
    play() {
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
      this.showScore=false
    },
    
    end(reactionTime) {
      this.isPlaying = false
      this.score= reactionTime
      this.showScore= true
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
