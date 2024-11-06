<template>
    <header>
        <h1><img :src="imagePath" width="40" height="40" alt="Movie Icon" /> {{ selectedMovieTitle }}</h1>
    </header>
  </template>
  
  <script>
  import { inject } from 'vue';
  export default {
    name: 'HeaderComponent',
    setup() {
        const selectedMovieTitle = inject("selectedMovieTitle"); 
        const imagePath = require('@/assets/camera.png');
        return { selectedMovieTitle, imagePath  };
    },
  };
  </script>
  
  <style scoped>
  header {
    text-align: center;
    font-size: 1rem;
    margin: 0;
    background-color: rgb(32 35 42);
    width: 100%;
    padding: 0;
    color: #fff;
    height: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  h1{
    margin: 0px;
    padding: 19px;
  }
  </style>
  