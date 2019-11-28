<template lang="html">
  <div>
    <ul>
      <favourite-item v-for="(favourite, index) in favourites" :favourite="favourite" :key="index"></favourite-item>
    </ul>

  </div>
</template>

<script>
import FavouriteItem from './FavouriteListItem.vue';

export default {
  name: "favourites-list",
  props: ['favourites'],
  components: {
    "favourite-item": FavouriteItem
  }
}
</script>

<style lang="css" scoped>
</style>
