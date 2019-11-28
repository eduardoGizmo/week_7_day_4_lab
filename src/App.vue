<template>
  <div id="app">
    <h1>Brewdog</h1>
    <div id="main-container">
      <beers-list :beers="beers"></beers-list>
    </div>
    <div>
      <beer-detail :beerToShow="selectedBeer"></beer-detail>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue';

export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedBeer: null
    };
  },
mounted(){
  fetch('https://api.punkapi.com/v2/beers')
  .then(res => res.json())
  .then(beers => this.beers = beers)

  eventBus.$on('beer-selected', (beer) => {
    this.selectedBeer = beer;
  })
},
components: {
  "beers-list": BeersList,
  "beer-detail": BeerDetail
}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
