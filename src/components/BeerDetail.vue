<template lang="html">
  <div v-if="beerToShow">
    <h3>{{beerToShow.name}}</h3>
    <img :src="beerToShow.image_url" alt="">
    <p>{{beerToShow.description}}</p>
    <button type="button" v-on:click="handleClickFav">Select as Favourite</button>

  </div>

</template>

<script>
import {eventBus} from '../main.js'
// import BeerDetail from './BeerDetail.vue'

export default {
  name: 'beer-detail',
  props: ['beerToShow'],
  methods: {
    handleClickFav(){
      eventBus.$emit('favourite-selected', this.beerToShow);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
