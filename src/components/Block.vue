<template lang="">
    <div v-if="showBlock" class="
     w-[400px] bg-[#0faf87] 
    text-white p-[100px] 
    m-10 text-xl 
    items-center font-bold
    text-center rounded-xl">
        Click me
    </div>
</template>
<script>
export default {
    props : ['delay'],
    data() {
        return {
            showBlock: false
        }
    },
    mounted(){
        console.log("component mounted");
        setTimeout(()=>{
            this.showBlock = true
            console.log("after: ", this.delay);
        } ,this.delay)
    },
    updated() {
        
    },
}
</script>
<style lang="">
    
</style>