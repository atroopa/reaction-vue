<template>
  <div class="flex flex-col items-center justify-between pt-10">
    <h1 class="text-red-900 text-3xl font-bold text-center">Open Code Reaction Timer</h1>
    <button 
      @click="start" 
      :disabled="isPlaying"
      :class="{'bg-red-300': isBlurred}"
      class="bg-red-900 px-4 py-2 my-3 rounded-2xl text-red-100">Play</button>
      <Result v-if="showResult" :score="score"/>
      <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  </div>
</template>

<!-- ------------- script --------------- -->

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
  export default {
    name : 'App',
    components : {
      Block,
      Result
    },
    data() {
      return {
        delay: 0.0,
        isPlaying: false,
        score: null,
        showResult: false,
        isBlurred: false
      }
    },
    methods: {
      start(){
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
        this.showResult = false
        this.isBlurred = true
        console.log(this.delay)

      setTimeout(() => {
        this.isBlurred = false;
      }, this.delay);
      },
      endGame(reactionTime){
        this.score = reactionTime
        this.isPlaying = false
        this.showResult = true
        this.isBlurred = false
      }
    }
  }
</script>
<!-- ------------- style --------------- -->
<style>

</style>
