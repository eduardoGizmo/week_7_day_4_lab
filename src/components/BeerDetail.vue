<template lang="html">
  <div v-if="beerToShow">
    <h3>{{beerToShow.name}}</h3>
    <img :src="beerToShow.image_url" alt="">
    <p>{{beerToShow.description}}</p>
    <button class="favouriteBtn" type="button" v-on:click="handleClickFav">Select as Favourite</button>

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
  img{
    height: 5%;
    width: 5%;
    }
    p{
      width: 50%;
      margin: auto;
    }
    button.favouriteBtn{
      background: #5a5af2;
      padding: 10px 34px;
      border-radius: 25px;
      font-size: 16px;
      margin: 20px auto;
      display: block;
      -webkit-transition: 0.3s ease-in-out;
      transition: 0.3s ease-in-out;
      cursor: pointer;
  }
    button.favouriteBtn:hover {
    transform: translateY(-5px);
}
</style>
