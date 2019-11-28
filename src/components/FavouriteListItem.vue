<template lang="html">
  <div v-if="favourite">
      <h1>{{favourite.name}}</h1>
  </div>
</template>

<script>
export default {
  name: "favourite-list-item",
  props: ['favourite']
}
</script>

<style lang="css" scoped>
</style>
