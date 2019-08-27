<template>
  <div v-if="headlines === null" class="home">
    <Spinner2/>
  </div>
  <div v-else class="home" >
    <section v-for="(headline, i) in headlines" :key="i" class="cardStack">
      
      <Card 
      v-for="(value, i) in headline"
      :key="i"
      :domain="value.domain"
      :category="value.category"
      :authorSrc="value.author"
      :dateSrc="value.date"
      :summarySrc="value.description"
      :imgSrc="value.imageUrl"
      :titleSrc="value.title"
      :linkSrc="value.link"
      />
      
      <LinkList
      v-for="(value, i) in headline"
      :key="i"
      :linkTitle1="value.title1"
      :linkDate1="value.date1"
      :linkUrl1="value.link1"
      :linkTitle2="value.title2"
      :linkDate2="value.date2"
      :linkUrl2="value.link2"
      :linkTitle3="value.title3"
      :linkDate3="value.date3"
      :linkUrl3="value.link3"
      :linkTitle4="value.title4"
      :linkDate4="value.date4"
      :linkUrl4="value.link4"
      :linkTitle5="value.title5"
      :linkDate5="value.date5"
      :linkUrl5="value.link5"
      :linkTitle6="value.title6"
      :linkDate6="value.date6"
      :linkUrl6="value.link6"
       />
    </section>
    
  <AnchorButton/>
  </div>
</template>

<style lang="scss" scoped>
@import '../Sass/abstracts/_mixins.scss';
.home {
  padding-top: 6rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: stretch;
  @include respond(phone) {
    padding-top: 4rem;
  }
  .cardStack {
    display: flex;
    flex: 1 0 auto;
    width: 100%;
    margin: 0 auto;
    flex-wrap: wrap;
    justify-content: center;
  }
}


</style>



<script>
// @ is an alias to /src


import Card from '../components/UI/Card';
import LinkList from '../components/UI/LinkList';
import Spinner2 from '../components/UI/Spinner2';
import AnchorButton from '../components/UI/CircleButton';



export default {
  name: 'home',
  components: {
    Card,
    LinkList,
    Spinner2,
    AnchorButton

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
