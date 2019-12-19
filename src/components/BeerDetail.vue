<template>
  <div v-if="beer">
    <h2>Name: {{beer.name}}</h2>
    <p>Description: {{beer.description}}</p>
    <p>ABV: {{beer.abv}}%</p>
    <img :src="beer.image_url" alt="" height="300px">
  </div>
</template>
<script>
export default {
  name: "beer-detail",

  props: ['beer']
}
</script>
<style lang="css" scoped>
</style>
