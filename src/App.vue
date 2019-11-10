<template>
  <div id="app">
    <h1>App</h1>
    <SelectedArticle :selected="selectedArticle" />
    <SearchBar @searchChange="getSearchTerm" />
    <NewsList @appAlert="appAlert"/>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import NewsList from './components/NewsList';
import SelectedArticle from './components/SelectedArticle';

export default {
  name: 'App',
  data() {
    return {
      query: '',
      selectedArticle: null
    }
  },
  components: {
    SearchBar,
    SelectedArticle,
    NewsList
  },
  methods: {
    getSearchTerm(query) {
      console.log('Query: ' + query);
    },
    appAlert(article) {
      this.selectedArticle = article;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px
}
</style>
