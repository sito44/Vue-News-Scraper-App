<template>
    <div class="cardContainer">
        <img :src="imgSrc" :alt="imgSrc">
        <div>
        <h2>{{titleSrc}}</h2>
        <h3><i>{{authorSrc}}</i></h3>
        <p>{{dateSrc}}</p>
        <p>{{summarySrc}}</p>
        <a :href="linkSrc">Source</a>
        </div>
        
    </div>
</template>

<script>
    export default {
        props: [
            'imgSrc', 
            'authorSrc',
            'titleSrc', 
            'dateSrc', 
            'summarySrc', 
            'linkSrc'],
        };
        
        
    
</script>

<style lang="scss" scoped>
    .cardContainer {
        position: relative;
        width: 20vw;
        
        margin: 1rem;
        flex:1 0 auto;
        background-color: rgba(white, 0.8);
        
        img {
            width: 100%;
            height:40%;
        }
        div {
            padding: .5rem 1rem 1rem 1rem;
            h2 {
                position: absolute;
                top:3rem;
                left:0rem;
                padding: 1rem;
                background-color: rgba(white,0.8);
                font-size: 1.5rem;
            }
            h3 {
                font-size: 1rem;
            }
            p {
                font-size: 1rem;
                margin-bottom: 2rem;
            }
            a {
                text-decoration: none;
                font-size: .8rem;
                background-color: rgba(230, 230, 230,0.8);
                color: #62716f;
                padding:.5rem 2rem;
                border-radius: .4rem;
            }
        }
    }
</style>