<template>
  <div class="about">
    <InfoCard :imgLocation="imgLocation" :copy="copy" :headingCopy="headingCopy"/>
  </div>
</template>

<script>
import InfoCard from '../components/UI/InfoCard';
const imgLocation = require('../assets/buttonsSvgs/molecular.svg');
  export default {
    components: {
      InfoCard
    },
    data() {
      return {
        imgLocation: imgLocation,
        copy: "Welcome to seek4truth.net, a modern web application built on JavaScript’s Node, Express, Vue runtime environment and libraries. Here you can find a variety of headlines scraped from multiple websites that are processed in parallel and presented in an elegant UI. Bringing global news headlines to you for the ultimate cross reference experience. Enjoy!" ,
        headingCopy: "Web Scrape Multi Source Tool"
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>
