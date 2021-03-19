<template>
<div class = "reviewContainer">
  <div class="movieInfo">
    <div class = "titleHeader">
      <h1>{{this.movie.title}}</h1>
    </div>
    <div class = "genreHeader">
      <h2 class = 'sectionTitle'><strong>Genre:</strong></h2>
      <h2 class="info">{{this.movie.genre}}</h2>
    </div>
    <div class ="revenueHeader">
      <div class ="revenueRow">
        <h2 class = 'sectionTitle'><strong>Box Office Revenue:</strong></h2>
        <h2 class="info">{{this.movie.box_office}}</h2>
      </div>
      <div class ="revenueRow">
        <h2 class = 'sectionTitle'><strong>Dave's Projected Box Office Revenue:</strong></h2>
        <h2 class="info">{{this.movie.dave_box_office}}</h2>
      </div>
    </div>
    <div class = 'daveComment'>
      <h3>Dave's Comments:</h3>
      <hr>
      <div class="comments">
        <p class="comment">{{this.movie.review}}</p>
        <div v-for="comment in this.movie.comments" :key="comment" @click="removeComment(comment)" class = 'trollComments'>
          <p class="comment">{{comment}}</p>
        </div>
        <p class="signature">--Dave</p>
      </div>
      <button @click="addComment()" class="trollButton">Troll Dave</button>
      <p class="buttonInfo">Press this button to add an extra comment to mess with Dave's review.</p>
      <p>Remove a comment by clicking it.</p>
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
  methods: {
    addComment() {
      let randomInt = Math.floor(Math.random() * Math.floor(100));
      this.movie.comments.push(this.$root.$data.movies[randomInt].review);
    },
    removeComment(comment) {
      const index = this.movie.comments.indexOf(comment);
      if (index > -1) {
        this.movie.comments.splice(index, 1);
      }
    }
  }

}
</script>

<style scoped>
  .movieInfo {
    text-align: left;
  }

  .signature {
    margin-left: 150px;
  }

  .info {
    font-weight: normal;
  }

  .comment {
    font-family: serif;
    font-size: 14pt;
  }
  .comments {
    margin-top: 10px;
    margin-bottom: 20px;
    padding-left: 20px;
  }

  .titleHeader,
  .genreHeader,
  .revenueRow {
    display: flex;
    flex-direction: row;
    padding:10px;
    padding-left: 35px;
  }

  .titleHeader {
    background-color: #5FA7FF;
    padding-bottom: 10px;
    font-size: 30px;
  }
  .genreHeader {
    background-color: #3879ef;
  }
  .revenueHeader {
    background-color: #5879ef;
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  }

  .sectionTitle {
    padding-right: 10px;
  }

  .daveComment {
    padding:5px;
    padding-left: 35px;
  }

  .reviewContainer {
    min-height: 100vh;
    padding-bottom: 2.5em;
  }

  .buttonInfo {
    padding-top: 10px;
  }

  .trollButton {
    background-color: #3879ef;
    padding: 10px 15px;
    border: none;
    font-weight: bold;
    width: 300px;
  }

  .trollButton:hover {
    background-color: #5879ef;
  }

  .trollButton:active {
    background-color: #8879ef;
    border: none;
  }

  h3 {
    font-size: 30px;
  }

  @media only screen and (max-width: 650px) {
    .titleHeader {
      font-size: 15px;
    }
  }
</style>
