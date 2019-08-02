<template>
  <div class="home">
    <Card 
    v-for="headline in headlines"
    :key="headline.title"
    :authorSrc="headline.author"
    :dateSrc="headline.date"
    :summarySrc="headline.description"
    :imgSrc="headline.imageUrl"
    :titleSrc="headline.title"
    :linkSrc="headline.link"
    ></Card>
  </div>
</template>

<style lang="scss" scoped>
.home {
  padding-top: 6rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>



<script>
// @ is an alias to /src
import Card from '../components/UI/Card';

export default {
  name: 'home',
  components: {
    Card
  },
  data() {
    return {
      headlines: []
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
