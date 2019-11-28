<template lang="html">
  <button class="favouriteBtn" v-on:click="handleClick">{{beer.name}}</button>
</template>

<script>
import {eventBus} from '../main.js'
import BeerDetail from './BeerDetail.vue'

export default {
  name: 'list-item',
  props: ['beer'],
  methods: {
    handleClick(){
      eventBus.$emit('beer-selected', this.beer);
      // console.log(this.beer);
    }
  }
}
</script>

<style lang="css" scoped>

button.favouriteBtn {
  font-weight: bold;
  background: #ffffff;
  padding: 10px 34px;
  /* border-radius: 25px; */
  font-size: 12px;
  margin: 4px 4px;
  /* display: block; */
  -webkit-transition: 0.3s ease-in-out;
  transition: 0.3s ease-in-out;
  cursor: pointer;
  /* color: #fff; */
  border: 1px solid gainsboro;
  box-shadow: 0 1px 6px -1px gainsbor
}
</style>
