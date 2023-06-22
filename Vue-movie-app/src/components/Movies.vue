<template>
    <div>
      <h1>Movies</h1>
      <div class="movies-container">
        <div class="movie-item" v-for="movie in movies" :key="movie.id">
            
            <a :href="'https://www.themoviedb.org/movie/' + movie.id" target="_blank">
                <img class="movie-img" :src="'https://image.tmdb.org/t/p/w300' + movie.poster_path" alt="">
            </a>
            <div class="movie-name">
                {{ movie.original_title }}
            </div>
            <div class="movie-average">
                Średnia ocen:
                {{ movie.vote_average }}
            </div>
            <div class="movie-release-date">
                Premiera:
                {{ movie.release_date }}
            </div>
            <div class="movie-overview">
                <p>Opis filmu:</p>
                {{ movie.overview }}
            </div>
        </div>
      </div>
    </div>
  </template>
  
  
  
  <script>
  
    import axios from 'axios';
  
    export default {
      data() {
        return {
          movies: [],
        };
      },
      mounted() {
        this.fetchMovies();
      },
      methods: {
        fetchMovies() {
          const URL = "https://api.themoviedb.org/3/movie/popular?api_key=93786018a448d0e4b3f64df0a4c9e46b";
  
          axios.get(URL)
            .then(response => {
              this.movies = response.data.results;
              console.log(response.data)
            })
            .catch(error => {
              console.log(error);
            });
        },
      },
    };
  
  </script>

  <style scoped>
    h1 {
        display: flex;
        justify-content: center;
        color: whitesmoke;
        font-size: 40px;
        font-weight: 600;
    }
    .movies-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        text-align: center;
        gap: 50px;
    }
    .movie-item {
        margin-bottom: 15px;
        width: 30%;
        box-sizing: border-box;
        align-items: center;
        color: white;
        background-color: grey;
        opacity: 1;
        border-radius: 35px;
        width: 400px;
        gap: 10px;
        padding: 12px;
    }
    .movie-img {
        border-radius: 3rem;
        box-shadow: 3rem;
        padding-top: 10px;
    }

    .movie-name {
        padding-top: 10px;
        font-size: 1.5rem;
        font-weight: bold;
        color: whitesmoke;
    }

    .movie-average,
    .movie-release-date,
    .movie-overview {
        display: block;
        padding-top: 10px;
        font-size: 1.2rem;
    }
  </style>
  