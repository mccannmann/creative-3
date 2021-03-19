<template>
  <div class="wrapper">
  <div class="movies">
    <div class="review" v-for="movie in favorites" :key="movie.title">
      <div class="titleBox">
        <h2 class="movieTitle">{{movie.title}}</h2>
      </div>
      <img :src="'/images/' + movie.dave_rank + '.png'">
      <div class="movieButtons">
        <div @click="removeFromFavorites(movie)" class="addFavorite">
          <p>Remove From Favorites</p>
        </div>
        <h1 class="divider">|</h1>
        <div class="toReview">
          <router-link :to="'/views/Review/' + movie.title">Dave's Review</router-link>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'FavMovies',
  props: {
    favorites: Array
  },
  methods: {
    removeFromFavorites(movie) {
      const index = this.$root.$data.favorites.indexOf(movie);
      if (index > -1) {
        this.$root.$data.favorites.splice(index, 1);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.movies {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.review {
  margin: 10px;
  margin-top: 50px;
  width: 300px;
  margin-bottom: 30px;
  background-color: #5FA7FF;
}

.review img {
  height: 250px;
  width: 250px;
  object-fit: cover;
}

.titleBox {
  height: 100px;
  width: 95%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.movieButtons {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  background-color: #3879EF;
}

.divider {
  margin: 0;
  color: white;
  font-size: 40px;
  font-family: serif;
}

.addFavorite,
.toReview {
  text-decoration: none;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50%;
}
.addFavorite:hover,
.toReview:hover {
  background-color: #5879ef;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: white;
  text-decoration: none;

}
</style>
