<template>
    <a href="#toTop"><button></button></a>
</template>



<style lang="scss" scoped>
@import '../../Sass/abstracts/_mixins.scss';
    button {
        position: fixed;
        bottom: 2rem;
        right:2rem;
        width: 5%;
        height: 10%;
        border-radius: 100%;
        border: none;
        transform: rotate(-90deg);
        background-image: url('../../assets/buttonsSvgs/arrows_right_double-31.svg');
        background-repeat: no-repeat;
        background-position: center;
        background-size: 85%;
        box-shadow: -2px 0px 4px black;
        opacity: .9;
        @include respond(big-desktop){
            height:10vh;
            width: 5vw;
            
        }
        @include respond(desktop) {
            height:10vh;
            width: 5vw;
            
         }
        @include respond(tab-land) {
            height:10vh;
            width: 7vw;
        }
        @include respond(tab-port) {
            height:6vh;
            width: 8vw;
        }
        @include respond(phone) {
            height:10vh;
            width: 18vw;
            bottom: 1rem;
            right:1rem;
            
        }
        
    }
</style>