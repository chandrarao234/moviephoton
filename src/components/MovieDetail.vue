<template>
    <div v-if="movie" class="movie-detail">
      <img :src="movie.image" alt="Movie Poster" />
      <h2>{{ movie.title }} ({{ movie.year }})</h2>
      <p><strong>Director:</strong> {{ movie.director ?   movie.cast.join(', ') : 'director' }}</p>
      <p><strong>Cast:</strong> {{ movie.cast ? movie.cast.join(', ') : ' cast' }}</p>
      <p><strong>Genre:</strong> {{ movie.genre ? movie.genre.join(', ') : 'genre' }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['selectedMovie'],
    computed: {
      movie() {
        return this.selectedMovie;
      }
    }
  };
  </script>
  
  
  <style scoped>
  .movie-detail {
    padding: 20px;
    width: 50%;
  }
  .movie-detail img {
    max-width: 100%;
    width: 300px;
    height: auto;
    border-radius:16px;
  }
  p{
    margin: 5px 0px;
  }
  </style>
  