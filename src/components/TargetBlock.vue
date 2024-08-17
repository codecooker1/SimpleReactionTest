<template>
  <div v-if="showBlock" class="block" @click="stopTimer">Click Me!</div>
</template>

<script>
export default {
  name: "TargetBlock",
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      Timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.Timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.Timer);
      this.$emit("gameEnd", this.reactionTime);
    },
  },
};
</script>

<style scoped>
.block {
  background-color: #04aa6d; /* Green */
  border: 1px solid green;
  border-radius: 8px;
  color: white;
  padding: 100px 32px;
  margin: 40px auto;
  width: 450px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  transition-duration: 0.4s;
}
</style>
