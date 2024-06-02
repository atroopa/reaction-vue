<template>
  <div class="flex flex-col items-center justify-between pt-10">
    <h1 class="text-red-900 text-3xl font-bold text-center">Open Code Reaction Timer</h1>
    <button @click="start">Play</button>
  </div>
  <router-view/>
</template>
<!-- ------------- script --------------- -->
<script>
  export default {
    name : 'App',
    components : {},
    data() {
      return {
        delay: null,
        isPlaying : false,
      }
    },
    methods: {
      start(){

      }
    }
  }
</script>

<!-- ------------- style --------------- -->
<style>

</style>
