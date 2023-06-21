<template>

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

</style>