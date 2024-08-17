<template>
  <h1>Simple Reaction time game!</h1>

  <button class="btn" :disabled="isPlaying" @click="start">Play !</button>

  <TargetBlock v-if="isPlaying" :delay="delay" @gameEnd="gameEnd" />

  <GameResult v-if="showResults" :score="score" />
</template>

<script>
import TargetBlock from "./components/TargetBlock.vue";
import GameResult from "./components/GameResult.vue";

export default {
  name: "App",
  components: { TargetBlock, GameResult },
  data() {
    return {
      isPlaying: false,
      delay: 2000,
      score: 0,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
    },
    gameEnd(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
  },
};
</script>

<style>
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #d3c1af;
}
#logo {
  max-width: 50px;
  margin: auto;
}
.btn {
  background-color: #04aa6d; /* Green */
  border: 1px solid green;
  border-radius: 8px;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  transition-duration: 0.4s;
}
.btn:hover {
  background-color: #04aa6dc4;
  box-shadow: 0 12px 16px 0 rgba(0, 0, 0, 0.24),
    0 17px 50px 0 rgba(0, 0, 0, 0.19);
}
.btn:disabled {
  background-color: #037c50;
  cursor: not-allowed;
}
</style>
