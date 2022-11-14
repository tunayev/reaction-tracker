<template>
  <p class="mt-5">Reaction Time: {{ score }}</p>
  <p class="text-green-600 text-3xl font-semibold mt-5">{{ level }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      level: null,
    };
  },
  methods: {
    calculateScore(score) {
      let level;
      switch (true) {
        case score < 500:
          level = "Meteoric!";
          break;
        case score < 1000:
          level = "Not bad";
          break;
        default:
          level = "You should continue to work on!";
      }
      return level;
    },
  },
  mounted() {
    this.level = this.calculateScore(this.score);
  },
};
</script>

<style></style>
