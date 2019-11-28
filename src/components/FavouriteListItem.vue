<template lang="html">
  <div v-if="favourite">
      <h3>{{favourite.name}}</h3>
      <h3>Alcoholic Content: {{favourite.abv}}</h3>
  </div>
</template>

<script>
export default {
  name: "favourite-list-item",
  props: ['favourite']
}
</script>

<style lang="css" scoped>
  div {
    border: black dotted 2px;
    margin: 0 5px;
    padding: 5px;
  }
</style>
