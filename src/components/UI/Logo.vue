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
@import '../../Sass/abstracts/_mixins.scss';
.imgContainer {
    flex:1 1 auto;
    text-align: left;
    align-self: center;
    @include respond(phone) {
        width: 1rem;
        img {
            width: 9rem;
        }
    }
    
}
</style>