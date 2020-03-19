<template> 
    <div>
        <i><b>{{ author }}</b></i>
        <p>{{ content }}</p>
    </div>
</template>

<script>
export default {
    name: "Tweet",
    props: {
        author: {
            type: String,
            required: true
        },
        content: {
            type: String,
            required: true
        }
    }    
}
</script>

<style scoped>

</style>