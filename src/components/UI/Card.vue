<template>
    <div class="cardContainer">
        <img :src="relativePathFilter(imgSrc)" :alt="imgSrc">
        <span>{{domain}}.com</span>
        <div>
        <h2>{{titleSrc}}</h2>
        <h3 v-if="authSrc"><i>{{authorSrc}}</i></h3>
        <p v-if="dateSrc">{{dateSrc}}</p>
        <p v-if="summarySrc">{{summarySrc}}</p>
        <a :href="linkSrc" target="_blank">Source</a>
        </div>
        
    </div>
</template>

<script>
    export default {
        props: [
            'domain',
            'imgSrc', 
            'authorSrc',
            'titleSrc', 
            'dateSrc', 
            'summarySrc', 
            'linkSrc'],
        methods: {
            relativePathFilter(strg) {
                return strg.match(/\b(\w*https\w*)\b/g) ?
                            this.imgSrc
                            :
                            `https://www.${this.domain}.com/${this.imgSrc.slice(1)}`;
            }
        }
        };
        
        
    
</script>

<style lang="scss" scoped>
    .cardContainer {
        position: relative;
        width: 24vw;
        align-self: auto;
        margin: 1rem;
        flex:1 0 auto;
        background-color: rgba(white, 0.8);
        
        
        img {
            width: 100%;
            height:40%;
            margin-bottom: 1rem;
        }
        span {
            font-size: .9rem;
        }
        div {
            padding: .5rem 1rem 1rem 1rem;
            h2 {
                position: absolute;
                top:1rem;
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