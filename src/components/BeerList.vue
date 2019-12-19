<template>
  <div>
    <ul>
      <list-item v-for="(beer, index) in beers" :key="index" :beer="beer"/>
    </ul>

  </div>
</template>
<script>
import ListItem from './ListItem.vue'
export default {
  name: "beer-list",
  data: () => ({

  }),
  props: ['beers'],
  components: {
    'list-item': ListItem
  }
}
</script>
<style lang="css" scoped>
</style>
