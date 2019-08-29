<template>
  <div id="app">
    <div id="navBar">
      <Logo :imglocation="logolocation"></Logo>
      <nav class="navigation">
      <router-link class="route-link" to="/">Home</router-link> |
      <router-link class="route-link"to="/about">About</router-link>
      </nav>
    </div>
    <div id="toTop"></div>
    <main>
      <router-view/>
    </main>
    <Footer class="flex-style">
      <ul class="flex-box">
        <li><a href="https://newatlas.com/" target="_blank">newatlas.com</a></li>
        <li><a href="https://www.sciencealert.com/" target="_blank">sciencealert.com</a></li>
        <li><a href="https://www.zerohedge.com/" target="_blank">zerohedge.com</a></li>
      </ul>
      <ul class="flex-box">
        <li><a href="https://naturalnews.com/" target="_blank">naturalnews.com</a></li>
        <li><a href="http://themindunleashed.com/" target="_blank">themindunleashed.com</a></li>
        <li><a href="https://www.consciouslifestylemag.com/" target="_blank">consciouslifestylemag.com</a></li>
      </ul>
       <ul class="flex-box">
        <li><a href="https://snlsnetwork.com/" target="_blank">snlsnetwork.com</a></li>
        <li><a href="http://news2share.com/" target="_blank">news2share.com</a></li>
        <li><a href="https://www.activistpost.com/" target="_blank">activistpost.com</a></li>
       </ul>
       <ul class="flex-box">
        <li><a href="https://thefreethoughtproject.com/" target="_blank">thefreethoughtproject.com</a></li>
        <li><a href="https://thefifthcolumnnews.com/" target="_blank">thefifthcolumnnews.com</a></li>
        <li><a href="https://truthinmedia.com/" target="_blank">truthinmedia.com</a></li>
       </ul>
       <ul class="flex-box">
        <li><a href="https://theconsciousresistance.com/" target="_blank">theconsciousresistance.com</a></li>
        <li><a href="https://www.mintpressnews.com/" target="_blank">mintpressnews.com</a></li>
        <li><a href="https://theantimedia.com/" target="_blank">theantimedia.com</a></li>
       </ul>
    </Footer>
  </div>
</template>

<script>
const logoImg = require('./assets/logos/seek4truthLogo_200x200.png');
import Logo from './components/UI/Logo.vue';
import Footer from './components/UI/Footer.vue';


export default {
  data() {
    return {
      logolocation: logoImg
    }
  },
  components: {
    Logo,
    Footer
  }
}
</script>

<style lang="scss">
@import './Sass/abstracts/_mixins.scss';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(98, 113, 111);
  width: 100vw;
  height: 100vh;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  overflow-x: hidden;
  font-size: 62.5%;
  background-image: url('./assets/patterns/escheresque.png');
  scroll-behavior: smooth;
  
  
}
#navBar {
  z-index:500;
  background: linear-gradient(to right, rgba(255,255,255,1), rgba(255,255,255,0.4));
  background-color: rgba(white, 0.8);
  width: 100%;
  padding: 0 0 0 .3rem;
  box-shadow: 0 -1px 5px black;
  position: fixed;
  display: flex;
  justify-content: space-between;
  .navigation {
    align-self: center;
    flex:1 0 auto;
    padding-right: 1rem;
    text-align: right;


  }
  .route-link {
    transition: all 0.2s ease;
    font-weight: bold;
    color: #2c3e50;
    font-size: 1rem;
    padding: 0 .8rem 0 .8rem;
    
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
main {
  margin-bottom: 10.8rem;
        @include respond(tab-land) {
          margin-bottom: 0;  
        }
        @include respond(tab-port) {
          margin-bottom: 0;
        }
        @include respond(phone) {
          margin-bottom: 0;
            
        }
}
.flex-style {
  display: flex;
  flex-wrap: wrap;

}
</style>
