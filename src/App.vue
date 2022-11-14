<template>
  <h1 class="text-3xl font-bold underline">Test your speed!</h1>
  <button @click="start" class="mt-5 bg-green-300" :disabled="started">
    Start!
  </button>
  <Block v-if="started" :delay="delay" />
</template>

<script>
import Block from "./components/Block.vue";
export default {
  components: { Block },
  name: "App",
  methods: {
    start() {
      this.started = true;
      this.delay = 1000 + Math.random() * 4000;
    },
  },
  data() {
    return {
      started: false,
      delay: null,
    };
  },
};
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
