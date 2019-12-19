<template>
  <div>
<li>{{beer.name}}</li>


  </div>
</template>
<script>
export default {
  name: "list-item",
  data: () => ({

  }),
  props: ['beer']
}
</script>
<style lang="css" scoped>
</style>
