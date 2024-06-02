<template lang="">
    <div>
        <p  class="font-bold text-lg text-green-900 ">Reaction Time: {{score}} mili second</p>
        <p>{{rank}}</p>
    </div>
</template>
<script>
export default {
    data() {
        return {
            rank: null,
        }
    },
    props: {
        score: Number
    }, 
    mounted() {
        if(this.score <= 250){
            this.rank = "عالی بود عالی"
        } else if(this.score <= 400){
            this.rank = "ای بدک نبود"
        } else {
            this.rank = "گشاد کی بودی تو "
        }
    },    
}
</script>
<style lang="">
    
</style>