<template>
  <div class="movie-list">
    <ul>
      <li v-for="movie in movies" :key="movie.id" @click="selectMovie(movie)">
        {{ movie.title }}
      </li>
    </ul>
  </div>
</template>

<script>
import movies from "../movies"; 
export default {
  data() {
    return {
      movies: movies, 
      selectedMovie: null
    };
  },
  methods: {
    selectMovie(movie) {
      this.$emit("movie-selected", movie); 
      this.selectedMovie = movie;
    }
  }
};
</script>


  <style scoped>
    .movie-list{
        background-color: #ececec;
        padding-top: 1em;
        width: 50%;
        display: flex;
        flex-direction: column;
    }
    .movie-list ul {
        list-style: none;
        padding: 0;
    }
    .movie-list li {
        padding: 10px;
        cursor: pointer;
    }
    .movie-list .selected {
        background-color: #ddd;
    }
  </style>
  