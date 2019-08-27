<template>
    <article class="cardContainer" >
        <span class="category" v-if="category">{{category}}</span>
        <img v-if="imgSrc" :src="relativePathFilter(imgSrc)" :alt="imgSrc">
        <h2>{{titleSrc}}</h2>
        <div>
        <h4 v-if="!domain.match(/\b(\w*snlsnetwork\w*)\b/g)">{{domain}}.com</h4>
        <h3 v-if="authorSrc"><i>{{authorSrc}}</i></h3>
        <h4 v-if="dateSrc"><i>{{dateSrc}}</i></h4>
        <p v-if="summarySrc">{{summarySrc}}</p>
        <a v-if="!domain.match(/\b(\w*snlsnetwork\w*)\b/g)" :href="linkSrc" target="_blank">Source</a>
        </div>
        
    </article>
</template>

<script>
    export default {
        props: [
            'domain',
            'category',
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
@import '../../Sass/abstracts/_mixins.scss';
    .cardContainer {
        position: relative;
        width: 18vw;
        align-self: auto;
        margin: 1rem;
        flex:1 0 auto;
        flex-wrap: nowrap;
        background: linear-gradient(to bottom, rgba(255,255,255,1), rgba(255,255,255,0));
        @include respond(desktop) {
            width: 26vw;
        }
        @include respond(tab-land) {
            width: 32vw;
        }
        @include respond(tab-port) {
            width: 40vw;
        @include respond(phone) {
            width: 100vw;
            
        }
        }

        .category {
            position: absolute;
            width: 100%;
            top: -1.7rem;
            padding:.3rem .5rem .3rem 0rem;
            right: 0rem;
            text-align: right;
            background: linear-gradient(to left, rgba(98, 113, 111, 1), rgba(255,255,255,0));
            text-shadow: 0 1px 1px black;
            color: white;
            font-size: .9rem;
            
            
        }
        
        img {
            width: 100%;
        }
        h2 {
            position: absolute;
            top:-1.3rem;
            left:0rem;
            padding: 1rem;
            background-color: rgba(white,0.8);
            font-size: 1.5rem;
            
            
        }
        div {
            padding: .5rem 1rem 1rem 1rem;
            z-index: 50;
            h4 {
                font-size: .9rem;
                font-weight: 400;
                
            }
            h3 {
                font-size: 1rem;
            }
            p {
                font-size: 1rem;
                margin-bottom: 2rem;
            }
            a {
                
                display: inline-block;
                text-decoration: none;
                font-size: .8rem;
                background-color: rgba(98, 113, 111, .6);
                color: white;
                padding:.5rem 2rem;
                border-radius: .4rem;
                transition: text-shadow .3s ease;
                
                &:hover {
                    text-shadow: 0 1px 1px white;
                    
                }
                
            }
        }
    }
</style>