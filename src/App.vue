<template>
  <div id="app" class="app-container">
    <Header />
    <div class="main-content">
      <MovieDetail :selectedMovie="selectedMovie" />
      <MovieList @movie-selected="updateSelectedMovie" />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MovieList from './components/MovieList.vue';
import MovieDetail from './components/MovieDetail.vue';
import { ref, provide } from 'vue';

export default {
  components: {
    Header,
    MovieList,
    MovieDetail
  },
  setup() {
    const selectedMovieTitle = ref("Movie Catalogue"); 
    const selectMovie = (movie) => {
      selectedMovieTitle.value = movie.title; 
    };

    provide("selectedMovieTitle", selectedMovieTitle);

    return { selectMovie };
  },
  data() {
    return {
      selectedMovie: null
    };
  },
  methods: {
    updateSelectedMovie(movie) {
      this.selectedMovie = movie;
      this.selectMovie(movie);
    }
  }
};
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
.app-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 75%;
  margin: 0 auto;
  border: 1px solid #ddd;
  font-family: "Roboto", serif;
}
.main-content {
  display: flex;
  width: 100%;
  height: 85vh;
  font-family: "Roboto", serif;
}
</style>
