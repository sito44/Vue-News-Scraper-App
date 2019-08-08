<template>
  <div v-if="headlines === null" class="home">
    <Spinner2/>
  </div>
  <div v-else class="home" >
    <div v-for="headline in headlines">
    <Card 
    v-for="value in headline"
    :key="value.title"
    :domain="value.domain"
    :authorSrc="value.author"
    :dateSrc="value.date"
    :summarySrc="value.description"
    :imgSrc="value.imageUrl"
    :titleSrc="value.title"
    :linkSrc="value.link"
    ></Card>
  </div>
  </div>
</template>

<style lang="scss" scoped>
.home {
  padding-top: 6rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}


</style>



<script>
// @ is an alias to /src
import Card from '../components/UI/Card';
import Spinner2 from '../components/UI/Spinner2';

export default {
  name: 'home',
  components: {
    Card,
    Spinner2

  },
  data() {
    return {
      headlines: null
    }
  },
  created() {
    this.fetchData();
  },
  updated() {
    console.log(this.headlines);
  },
  methods: {
    fetchData() {
      let vm = this;
      this.$http.get('https://whispering-island-74529.herokuapp.com/api/initial-scrape')
      .then(res => {
        return res.json();
      })
      .then(data => {
        console.log(data);
        vm.headlines = data;
      })
      .catch(err => console.log(err));
    }
  }
}
</script>
