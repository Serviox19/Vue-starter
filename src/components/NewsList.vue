<template>
  <div id="news">
    <ul>
      <li v-for="article in news" v-bind:key="article.title">
        {{ article.title }}
      </li>
    </ul>
  </div>
</template>


<script>
  import axios from 'axios';

  export default {
    name: 'NewsList',
    mounted() {
      this.getNews()
    },
    data() {
      return {
        news: []
      }
    },
    components: {},
    methods: {
      getNews() {

        axios.get('https://newsapi.org/v2/top-headlines?country=us&apiKey=b1eff68325b04271adb0e4956da610b4').then(response => this.news = response.data.articles)

      }
    }
  }
</script>


<style></style>
