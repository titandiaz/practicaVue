<template>
  <main role='main' class='movie-wrapper'>
    <h1>{{ title }}</h1>
    <movie v-bind:selected-movie='selectedMovie'></movie>>
  </main>
</template>

<script>
import Vue from 'vue'
import Movie from '@/components/movie/Movie'

export default{
  name: 'app',
  components: {
    Movie 
  },
  data () {
    return {
      title: 'Movues: find your tonight\'s pla',
      selectedMovie:{}
    }
  },
  mounted: function() {
    this.searchMovie('sharknado');
  },
  methods: {
    searchMovie (movie) {
      return window.fetch(`${Vue.config.movues.ENDPOINT}${movie}`)
        .then(response => {
          return response.json();
        })
        .then(json => {
          this.selectedMovie = json;
        });
    }
  }
}
</script>



<style>

  html,
  body {
    color: #fff;
    background: rgb(37, 0, 0);
    font-family: 'Open Sans', sans-serif;
    background: linear-gradient(to bottom, #1e2339 40%, #425ebc 100%);
    margin: 0;
    padding: 0;
  }

  .movie-wrapper {
    height: 100vh;
    max-width: 800px;
    width: 90%;
    margin: 0 auto;
  }

  .movie-wrapper > h1 {
    font-weight: 300;
    text-align: center;
    margin: 0;
    padding: 2rem;
  }

</style>

