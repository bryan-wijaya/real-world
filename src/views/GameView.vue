<template>
  <div class="game">
    <h1>Ninja Reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Start Game</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
    <Result v-if="showResult" :score="score"/>
  </div>
</template>

<script>
import Block from '@/components/BlockDiv.vue';
import Result from '@/components/ResultDiv.vue';
export default {
  name: "Game",
  components: {Block, Result},
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    };
  },
  methods: {
    start(){
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTimer){
      this.score = reactionTimer
      this.isPlaying = false
      this.showResult = true
      console.log(reactionTimer);
    }
  }
};
</script>

<style>
#game {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}

.game h1{
  color: #444;
}

.game button{
  background: #0faf87;
  color:white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
.game button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>