<template>
  <div>
<li>{{beer.name}}
<button v-on:click="handleClick" type="button">More Information</button>
<button v-on:click="addFavourite" type="button">Add to favourites</button>

</li>


  </div>
</template>
<script>
import { eventBus } from '../main.js'
export default {
  name: "list-item",
  data(){
    return {
      favoriteBeer: this.beer
    }
  },
  methods: {
    handleClick(){
      eventBus.$emit('select-beer', this.beer);

    },
    addFavourite(){
      this.favouriteBeer = this.beer;
      eventBus.$emit('add-favourite', this.beer)
      this.favoriteBeer = null;
      console.log('click');
    }
  },
  props: ['beer']
}
</script>
<style lang="css" scoped>
</style>
