<template>
    <div id="display" v-if="layoutStyle" v-bind:style="GridStyle">                
        <Tweet id="item" v-for="tweet in Tweets"
            v-bind:author="tweet.author"
            v-bind:content="tweet.content"
            v-bind:key="tweet.content" 
        ></Tweet>
    </div>
    <div id="display" v-else v-bind:style="ListStyle">
        <Tweet id="item" v-for="tweet in Tweets"
            v-bind:author="tweet.author"
            v-bind:content="tweet.content"
            v-bind:key="tweet.content"
        ></Tweet>
    </div>
</template>

<script>
import Tweet from './Tweet.vue'

export default {
    name: 'List',
    components: {
       Tweet
    },
    data: function() {
        return {
            Tweets: [
                {
                    author:  "Author A",
                    content: "This is Author A's  Tweet"
                },
                {
                    author:  "Author B",
                    content: "This is Author B's  Tweet"
                },
                {
                    author:  "Author C",
                    content: "This is Author C's  Tweet"
                },
                {
                    author:  "Author D",
                    content: "This is Author D's  Tweet"
                },
                {
                    author:  "Author E",
                    content: "This is Author E's  Tweet"
                },
                {
                    author:  "Author F",
                    content: "This is Author F's  Tweet"
                },
                {
                    author:  "Author G",
                    content: "This is Author G's  Tweet"
                }
            ],
            GridStyle: {
                'display': 'grid',
                'grid-template-columns': 'repeat(auto-fill,minmax(20rem, 1fr))',                
                'padding': '0 5rem',
                'margin': '5rem auto',
                'max-width': '80rem'                 
            },
            ListStyle: {
                'display': 'grid',
                'grid-template-columns': 'auto', 
                'padding': '10px',
                'margin-left': '37vw'
            },
            layoutStyle: true
        }
        
    },
    mounted: function(){
        this.$root.$on('changeTweetStyle', this.changeTweetLayout);
    },
    methods: {
        changeTweetLayout: function(data) {            
                this.layoutStyle = data;          
            console.log(this.layoutStyle);            
        }
    }
}
</script>

<style scoped>

#item {
    width: 20vw;
    height: 20vh;    
    padding-top: 60px;
    margin: 10px; 
    border-radius: 0.75rem;
    background-color: white; 
    box-shadow: 10px 10px 20px grey;  
}
</style>