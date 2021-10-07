<template>
  <div id="app">
    <Header @searching="searchFilm"/>
    <Films :films="films" :serie="serieTv"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Films
  },
  data() {
    return {
      films: [],
      serieTv: [],
      apiKey: '8849ab40e70f3d1178f18683527a0a04'
    }
  },
  methods: {
    searchFilm(query) {
      const params = {
        api_key: this.apiKey,
        query: query,
        language: 'it-IT',
      }
      // Chiamata per i films
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: params
      })
      .then( (response) => {
        // console.log(response.data);
        this.films = response.data.results;
      });
      // Chiamata per le serie tv
      axios.get('https://api.themoviedb.org/3/search/tv', {
        params: params
      })
      .then( (response) => {
        // console.log(response.data);
        this.serieTv = response.data.results;
      });
    }
  }
}
</script>

<style lang="scss">

</style>
