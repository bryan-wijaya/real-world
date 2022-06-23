<template>
  <div v-if="showBlock" class="block" @click="stopTimer">
    click me
  </div>
</template>
<script>
export default {
  props: ["delay"],
  data(){
    return {
      showBlock: false,
      timer: null,
      reactionTimer: 0
    }
  },
  methods: {
    startTimer(){
      this.timer = setInterval(() => {
        this.reactionTimer += 10;
      }, 10);
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end', this.reactionTimer)
      console.log(this.reactionTimer)
    }
  },
  mounted() {
    console.log("component mounted")
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay);
  },
  updated() {
    console.log("updated ")
  },
  unmounted() {
    console.log("unmounted")
  }
};
</script>
<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    cursor: pointer;
  }
</style>
