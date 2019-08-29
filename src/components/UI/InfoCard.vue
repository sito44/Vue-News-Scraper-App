<template>
    <div>
        
        <img :src="imgLocation" alt="network image">
        <h2>{{ headingCopy }}</h2>
        <p>{{ copy }}</p>
    </div>
</template>

<script>
    export default {
        props: [
            'imgLocation',
            'copy',
            'headingCopy'
        ]
    }
</script>

<style lang="scss" scoped>
@import '../../Sass/abstracts/_mixins.scss';
div {
    background-color: rgba(255, 255, 255, 0.7);
    width: 50vw;
    margin: 6rem auto 0 auto;
    padding: 4rem;
    font-size: 1.4rem;
        @include respond(phone) {
            padding: 3rem 0 3rem 0;
            width: 100vw;
        }
    img {
        width:10vw;
        margin-bottom: 2rem;
        @include respond(tab-land) {
           width:15vw;
        }
        @include respond(tab-port) {
            width:15vw;
        }
        @include respond(phone) {
          width:30vw;
            
        }
    }
    h2 {       
        @include respond(phone) {
            
        }
    }
    p {
        text-align: center;
        font-size: 1.2rem;
        @include respond(phone) {
            
        }
    }
}
</style>