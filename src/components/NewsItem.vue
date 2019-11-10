<template>
  <li class="news_item">
    <img class="poster" :src="getImgSrc" />
    <a class="link" :href="article.url" target="_blank" @click="onArticleClick">
      <h2 class="title">{{ article.title }}</h2>
      <p v-if="article.description" class="description">{{ article.description }}</p>
    </a>
    <div class="bottom">
      <span class="author" style="text-align:left">{{ article.author }}</span>
      <span class="created">{{ article.publishedAt }}</span>
    </div>
  </li>
</template>

<script>
  export default {
    name: 'NewsItem',
    computed: {
      getImgSrc() {
        if (this.article.urlToImage) {
          console.log('yes');
          return this.article.urlToImage
        } else {
          return "https://via.placeholder.com/400X400"
        }
      }
    },
    props: ['article'], //no need to use this.props, just use this.article
    mounted() {},
    methods: {
      onArticleClick() {
        this.$emit('toggleAlert', this.article)
      }
    }
  }
</script>

<style scoped>

.news_item {
  display: flex;
  flex-direction: column;
  background: #eee;
  padding: 1em;
  max-width: 500px;
  margin: 0 auto 2em
}

.link {
  display: inline-block;
  text-decoration: none;
  text-align: left
}

.title {
  margin: 0;
  font-size: 1em;
  color: #191919
}

.description {
  margin-top: 0.5em;
  margin-bottom: 0;
  color: #484848
}

.bottom {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 1.5em;
  color: #191919;
  font-weight: 500
}

.poster {
  width: 100%;
  height: 15em;
  object-fit: fill;
  margin-bottom: 1em
}

</style>
