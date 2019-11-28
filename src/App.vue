<template>
  <div id="app">
    <h1>Brewdog</h1>
    <div id="main-container">
      <beers-list :beers="beers"></beers-list>
    </div>
    <div>
      <beer-detail :beerToShow="selectedBeer"></beer-detail>
    </div>
    <div>
      <favourites-list :favourites="favourites"></favourites-list>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue';
import FavouritesList from './components/FavouritesList.vue';
import FavouriteListItem from './components/FavouriteListItem.vue';

export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedBeer: null,
      favourites: []
    };
  },
mounted(){
  fetch('https://api.punkapi.com/v2/beers')
  .then(res => res.json())
  .then(beers => this.beers = beers)

  eventBus.$on('beer-selected', (beer) => {
    this.selectedBeer = beer;
  })
  eventBus.$on('favourite-selected', (favourite) => {
    this.favourites.push(favourite);
  })
},
components: {
  "beers-list": BeersList,
  "beer-detail": BeerDetail,
  "favourites-list": FavouritesList,
  "favourite-list-item": FavouriteListItem
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
