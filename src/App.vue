<template>
  <div id="app">
    <Header @searching="searchFilm"/>
    <Films :films="films"/>
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
      films: []
    }
  },
  methods: {
    searchFilm(query) {
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: '8849ab40e70f3d1178f18683527a0a04',
          query: query,
          language: 'it-IT',
        }
      })
      .then( (response) => {
        // console.log(response.data);
        this.films = response.data.results;
      });
    }
  }
}
</script>

<style lang="scss">

</style>
