<template>
    <div>
      <h1>The most popular TVs!</h1>
      <div class="tvs-container">
        <div class="tv-item" v-for="tv in tvs" :key="tv.id">
            
            <a :href="'https://www.themoviedb.org/tv/' + tv.id" target="_blank">
                <img class="tv-img" :src="'https://image.tmdb.org/t/p/w300' + tv.poster_path" alt="">
            </a>
            <div class="tv-name">
                {{ tv.original_name }}
            </div>
            <div class="tv-average">
                Średnia ocen:
                {{ tv.vote_average }}
            </div>
            <div class="tv-release-date">
                Premiera:
                {{ tv.first_air_date }}
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
                tvs: [],
            };
        },
        mounted() {
            this.fetchTvs();
        },
        methods: {
            fetchTvs() {
                const TvsURL = "https://api.themoviedb.org/3/tv/popular?api_key=93786018a448d0e4b3f64df0a4c9e46b";

                axios.get(TvsURL)
                .then(response => {
                    this.tvs = response.data.results;
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
.tvs-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    text-align: center;
    gap: 50px;
}
.tv-item {
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
.tv-img {
    border-radius: 3rem;
    box-shadow: 3rem;
    padding-top: 10px;
}

.tv-name {
    padding-top: 10px;
    font-size: 1.5rem;
    font-weight: bold;
    color: whitesmoke;
}

.tv-average,
.tv-release-date {
    display: block;
    padding-top: 10px;
    font-size: 1.2rem;
}
</style>