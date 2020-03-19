<template>
    <button id="buttonStyle" :class="{toggled: toggleFlag}" @click="showTweets">Toggle</button>
</template>

<script>
export default {  
    
    data: function(){
        return {
            toggleFlag: false
        }        
    },
    methods: {
        showTweets() {                       
            this.$root.$emit('changeTweetStyle', this.toggleFlag);
            this.toggleFlag = !this.toggleFlag ;
        }
    }
}
</script>

<style scoped>
#buttonStyle {
    width: 10vw;
    height: 10vh;
    background: black;
    color: white;
    font-size: 20px;
}
</style>