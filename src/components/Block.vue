<template lang="">
    <div
    @click="stopTimer" 
    v-if="showBlock" 
    class="
        w-[400px] bg-[#0faf87] 
        text-white p-[100px] 
        m-10 text-xl 
        items-center font-bold
        text-center rounded-xl">
        Click me
    </div>
</template>

<!-- ------------- script --------------- -->

<script>
export default {
    props : ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTimer: 0
        }
    },
    mounted(){
        console.log("component mounted");
        setTimeout(()=>{
            this.showBlock = true
            this.startTimer()
            console.log("after: ", this.delay);
        } ,this.delay)
    },
    updated() {
        console.log("Component Updated");
    },
    unmounted() {
        console.log("component unmounted");
    },
    methods: {
        startTimer(){
            this.timer = setInterval(() => {
                this.reactionTimer += 10
            }, 10)
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit('end', this.reactionTimer)
        }
    },
}
</script>
