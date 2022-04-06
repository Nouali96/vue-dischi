<template>
  <div id="app">
    <Header @selectedGenreE="setSelectedGenre" :genresList="genresList"/>
    <Main @genresReady="setGenres" :selectedGenre="selectedGenre"/>
  </div>
</template>

<script>
import Header from './components/Header';
import Main from './components/Main';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return{
      genresList: [],
      selectedGenre: '',
    }
  },
  methods: {
    setGenres(genresListE) {
      this.genresList = genresListE;
    },
    setSelectedGenre(selectedGenreE) {
      this.selectedGenre = selectedGenreE;
    }  
  }
}
</script>

<style lang="scss">
@import "./assets/styles/general";
</style>
