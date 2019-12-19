<template>
  <div>
    <h1>Brewdog</h1>
    <beer-list :beers="beers"/>
    <beer-detail :beer="selectedBeer"/>
    <h2>Favorite Beers</h2>
    <beer-list :beers="favouriteBeers"/>
  </div>
</template>
<script>
import BeerList from './components/BeerList.vue';
import { eventBus } from './main.js';
import BeerDetail from './components/BeerDetail.vue';
export default {
  name: "app",
  data(){
    return {
      beers: [],
      selectedBeer: null,
      favouriteBeers: []
    }
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)


    eventBus.$on('select-beer', (beer) => {
      this.selectedBeer = beer
    }),
    eventBus.$on('add-favourite', (beer) => {
      console.log('recieved', beer);
      if (!this.favouriteBeers.includes(beer)){
        this.favouriteBeers.push(beer)
      }

    })
  },
  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail
  }

}
</script>
<style lang="css" scoped>
</style>
