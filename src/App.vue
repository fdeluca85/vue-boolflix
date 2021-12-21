<template>
  <div id="app">
      <Header @ricerca='searching'/>
      <Main :movies="movies" :series="series"/>
  </div>
</template>

<script>
import Header from './components/macro/Header.vue';
import Main from './components/macro/Main.vue';
import axios from 'axios'

export default {
  name: 'App',
  components: {
      Header,
      Main
  },
  data() {
    return {
      movies:[],
      series:[]
    }
  },
  methods: {
    searching(payload){
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'd709e60f4da8bcd79a37874605d0272c',
          query: payload,
          language: 'it-IT'
          }
      })
          .then((response) => {
            console.log(response.data.results);
            this.movies = response.data.results;
            // console.log(this.movie);
         })
          .catch(function (error) {
            console.log(error);
            })
      
      axios.get('https://api.themoviedb.org/3/search/tv', {
        params: {
          api_key: 'd709e60f4da8bcd79a37874605d0272c',
          query: payload,
          language: 'it-IT'
          }
      })
          .then((response) => {
            console.log(response.data.results);
            this.series = response.data.results
            // console.log(this.movie);
         })
          .catch(function (error) {
            console.log(error);
            })
    }
  }
}
</script>

<style lang="scss">
</style>