<template>
  <div>
    <Header></Header>
    <Movies></Movies>
  </div>
</template>



<script>

  import Movies from './components/Movies.vue';
  import Header from './components/Header.vue';
  import Tvs from './components/Tvs.vue';

  export default {
    components: {
      Header,
      Movies,
      Tvs,
    },
  }

</script>

<style scoped>

</style>
