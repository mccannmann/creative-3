<template>
  <div class="favorites">
    <img alt="Dave" src="../assets/Dave.png">
    <div v-if="this.$root.$data.favorites.length > 1">
      <h3 class = 'title'>Your Absolute Favorite Movies!</h3>
    </div>
    <div v-else-if="this.$root.$data.favorites.length > 0">
      <h3 class = 'title'>Your Absolute Favorite Movie!</h3>
    </div>
    <div v-else>
      <h3 class = 'title'>Dave says, "Why do you hate movies?"</h3>
    </div>
    <FavMovies :favorites = "favorites"/>
  </div>
</template>

<script>
// @ is an alias to /src
import FavMovies from '../components/FavMovies.vue'

export default {
  name: 'Favorites',
  components: {
    FavMovies
  },
  computed: {
    favorites(){
      return this.$root.$data.favorites;
    }
  }
}
</script>

<style scoped>
  .title {
    font-size: 60px;
    margin: 5px;
  }
</style>
