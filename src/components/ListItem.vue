<template>
  <div>
<li v-on:click="handleClick">{{beer.name}}</li>


  </div>
</template>
<script>
import { eventBus } from '../main.js'
export default {
  name: "list-item",
  data: () => ({

  }),
  methods: {
    handleClick(){
      eventBus.$emit('select-beer', this.beer);
      
    }
  },
  props: ['beer']
}
</script>
<style lang="css" scoped>
</style>
