<template lang="html">
  <div v-if="beerToShow">
    <h3>{{beerToShow.name}}</h3>
    <img :src="{{beerToShow.image_url}}" alt="">
    <p>{{beerToShow.description}}</p>

  </div>

</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beerToShow']
}
</script>

<style lang="css" scoped>
</style>
