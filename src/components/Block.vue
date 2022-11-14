<template>
  <div
    class="h-[200px] w-[400px] bg-blue-200 rounded-xl text-center my-10"
    v-if="showBlock"
  ></div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
    }, this.delay);
  },
};
</script>

<style></style>
