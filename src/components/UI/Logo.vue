<template>
    <div class="imgContainer">
        <img :src="imglocation" alt="seek4truthLogo">
    </div>
</template>

<script>
    export default {
        props: {
            imglocation: {
                type: String,
                required: true 
            },
        },
    }
</script>

<style lang="scss" scoped>
.imgContainer {
    flex:1 1 auto;
    text-align: left;
    align-self: center;
    img {
        max-width: 80%;
        height: 100%;
        
        
    }
}
</style>