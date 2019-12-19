<template>
  <div>
    <h1>Brewdog</h1>
    <beer-list :beers="beers"/>
  </div>
</template>
<script>
import BeerList from './components/BeerList.vue'
export default {
  name: "app",
  data: () => ({
    beers: []
  }),
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)

  },
  components: {
    "beer-list": BeerList
  }

}
</script>
<style lang="css" scoped>
</style>
