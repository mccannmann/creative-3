<template>
  <div class="home">
    <img alt="Dave" src="../assets/Dave.png">
    <h3 class = 'title'>Dave's Movie Reviews</h3>
    <div class="wrapper">
      <div class="search">
        <form class="pure-form">
          <i class="fas fa-search"></i><input v-model="searchText" />
        </form>
      </div>
    </div>
    <Movies :movies = "movies"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Movies from '../components/Movies.vue'

export default {
  name: 'Home',
  components: {
    Movies
  },
  data() {
    return {
      searchText: ''
    }
  },
  computed: {
    movies(){
      return this.$root.$data.movies.filter(movie => movie.title.toLowerCase().search(this.searchText.toLowerCase()) >=0);
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}

h3 {
  font-size: 60px;
  margin: 5px;
}
</style>
