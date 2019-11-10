<template>
  <div id="news">
    <ul>
      <NewsItem
        v-for="article in news"
        :article="article"
        :key="article.title"
        @toggleAlert="sendAlert"
      />
    </ul>
  </div>
</template>


<script>
  import axios from 'axios';
  import NewsItem from './NewsItem'

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
    components: {
      NewsItem
    },
    methods: {
      getNews() {
        axios.get('https://newsapi.org/v2/top-headlines?country=us&apiKey=b1eff68325b04271adb0e4956da610b4').then(response => this.news = response.data.articles)
      },
      sendAlert(article) {
        this.$emit('appAlert', article)
      }
    }
  }
</script>


<style></style>
