<template>
<div>
  <div class="movieInfo">
    <div class = "titleHeader"
      <h1>{{this.movie.title}}</h1>
    </div>
    <div class = "genreHeader">
      <h2>Genre</h2>
      <p>{{this.movie.genre}}</p>
    </div>
    <div class "revenueHeader">
      <h2>Box Office Revenue</h2>
      <p>{{this.movie.box_office}}</p>
      <h2>Dave's Projected Box Office Revenue</h2>
      <p>{{this.movie.dave_box_office}}</p>
    </div>
  <h3>Dave's Comments:</h2>
    <hr>
  <p>{{this.movie.review}}</p>
  <h3>Comments:</h2>
    <hr>
</div>
</div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      movie: {},
    }
  },
  created() {
    this.movie = this.$root.$data.movies.find(movie => movie.title === this.$route.params.title);
  },

}
</script>

<style scoped>
  .movieInfo {
    text-align: left;
  }

  .titleHeader,
  .genreHeader,
  .revenueHeader{
    display: flex;
    flex-direction: row;
  }

  .titleHeader {
    background-color: #5FA7FF;
  }
  .genreHeader {
    background-color: #3879ef;
  }
  .revenueHeader {
    background-color: #5879ef;
  }

  h3 {
    font-size: 30px;
  }
</style>
