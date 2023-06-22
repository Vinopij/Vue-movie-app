<template>
    <button @click="toggleMode">{{ buttonText }}</button>
  </template>
  
  <script>
  export default {
    data() {
      return {
        displayMovies: true,
      };
    },
    computed: {
      buttonText() {
        return this.displayMovies ? 'Show TVs' : 'Show Movies';
      },
    },
    methods: {
      toggleMode() {
        this.displayMovies = !this.displayMovies;
        this.$emit('mode-changed', this.displayMovies);
      },
    },
  };
  </script>

<style scoped>
    button {
        height: 50px;
        width: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
        border: 1px solid #032541;
        background-color: #084b81;
        border-radius: 8px;    
        color: white;    
    }
    button:hover {
        cursor: pointer;
    }
</style>