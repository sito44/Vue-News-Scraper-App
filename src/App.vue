<template>
  <div id="app">
    <div id="navBar">
      <Logo :imglocation="logolocation"></Logo>
      <nav class="navigation">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
      </nav>
    </div>
    <router-view/>
  </div>
</template>

<script>
const logoImg = require('./assets/logos/seek4truthLogo_200x200.png');
import Logo from './components/UI/Logo.vue';


export default {
  data() {
    return {
      logolocation: logoImg
    }
  },
  components: {
    Logo
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #62716f;
  width: 100vw;
  height: 100vh;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  overflow-x: hidden;
  font-size: 62.5%;
  background-image: url('./assets/patterns/escheresque.png');
  
  
}
#navBar {
  z-index:500;
  background-color: rgba(white, 0.8);
  width: 100%;
  padding: 0 0 0 .3rem;
  box-shadow: 0 1px 2px black;
  position: fixed;
  display: flex;
  justify-content: space-between;
  .navigation {
    align-self: center;
    flex:1 0 auto;
    padding-right: 1rem;
    text-align: right;


  }
  a {
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
</style>
