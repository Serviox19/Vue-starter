<template>
  <div id="app">
    <h1>App</h1>
    <SearchBar v-on:searchChange="getSearchTerm" />
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';

export default {
  name: 'App',
  data() {
    return {
      query: ''
    }
  },
  components: {
    SearchBar
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
