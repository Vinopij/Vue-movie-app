<template>
  <div>
    <Header></Header>
    <div class="btn">
    <Button @mode-changed="toggleDisplayMode"></Button>
    </div>
    <Movies v-if="displayMovies"></Movies>
    <Tvs v-if="!displayMovies"></Tvs>
  </div>
</template>



<script>
  import Button from './components/Button.vue'
  import Movies from './components/Movies.vue';
  import Header from './components/Header.vue';
  import Tvs from './components/Tvs.vue';

  export default {
    data() {
      return {
        displayMovies: true,
      };
    },
    methods: {
      toggleDisplayMode(displayMovies) {
        this.displayMovies = displayMovies;
      },
    },
    components: {
      Button,
      Header,
      Movies,
      Tvs,
    },
  }

</script>

<style scoped>
  .btn {
    display: flex;
    justify-content: center;
  }
</style>
