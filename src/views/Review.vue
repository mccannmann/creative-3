<template>
<div class = "reviewContainer">
  <div class="movieInfo">
    <div class = "titleHeader">
      <h1>{{this.movie.title}}</h1>
    </div>
    <div class = "genreHeader">
      <h2 class = 'sectionTitle'><strong>Genre:</strong></h2>
      <h2>{{this.movie.genre}}</h2>
    </div>
    <div class ="revenueHeader">
      <div class ="revenueRow">
        <h2 class = 'sectionTitle'><strong>Box Office Revenue:</strong></h2>
        <h2>{{this.movie.box_office}}</h2>
      </div>
      <div class ="revenueRow">
        <h2 class = 'sectionTitle'><strong>Dave's Projected Box Office Revenue:</strong></h2>
        <h2>{{this.movie.dave_box_office}}</h2>
      </div>
    </div>
    <div class = 'daveComment'>
      <h3>Dave's Comments:</h3>
      <hr>
      <h2>{{this.movie.review}}</h2>
      <div class = 'trollComments'>
        <button>Troll Dave</button>
        <p>Press this button to add an extra comment to mess with Dave's head</p>
      </div>
    </div>
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
  .revenueRow {
    display: flex;
    flex-direction: row;
    padding:5px;
    padding-left: 15px;
  }

  .titleHeader {
    background-color: #5FA7FF;
  }
  .genreHeader {
    background-color: #3879ef;
  }
  .revenueHeader {
    background-color: #5879ef;
    display: flex;
    flex-direction: column;
  }

  .sectionTitle {
    padding-right: 10px;
  }

  .daveComment {
    padding:5px;
    padding-left: 15px;
  }

  h3 {
    font-size: 30px;
  }
</style>
