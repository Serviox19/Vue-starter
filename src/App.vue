<template>
  <div id="app">
    <h1>App</h1>
    <SearchBar @searchChange="getSearchTerm" />
    <NewsList />
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import NewsList from './components/NewsList'

export default {
  name: 'App',
  data() {
    return {
      query: ''
    }
  },
  components: {
    SearchBar,
    NewsList
  },
  methods: {
    getSearchTerm(query) {
      console.log('Query: ' + query);
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
