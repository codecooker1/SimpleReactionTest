<template>
  <p>Reaction time: {{ score }}</p>

  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  name: "GameResult",
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score <= 200) {
      this.rank =
        "Were you born with cat-like reflexes, or is that a new skill? 🐱";
    } else if (this.score <= 400) {
      this.rank = "Quick, but I bet you could do better with caffeine. ☕";
    } else if (this.score <= 600) {
      this.rank =
        "You had enough time to contemplate the meaning of life before reacting. 🤔";
    } else if (this.score <= 800) {
      this.rank =
        "You had enough time to contemplate the meaning of life before reacting. 🤔";
    } else {
      this.rank = "Did you take a nap between the stimulus and response? 😴";
    }
  },
};
</script>

<style>
.rank {
  color: #04aa6d;
  font-style: bold;
  font-size: 1.4em;
}
</style>
