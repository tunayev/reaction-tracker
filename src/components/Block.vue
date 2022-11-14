<template>
  <div
    class="h-[200px] w-[400px] bg-blue-200 rounded-xl text-center my-10"
    v-if="showBlock"
    @click="stopTimer"
  ></div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
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
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
    },
  },
};
</script>

<style></style>
