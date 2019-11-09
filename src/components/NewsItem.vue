<template>
  <li class="news_item">
    {{ article.title }}
  </li>
</template>

<script>
  export default {
    name: 'NewsItem',
    props: ['article']
  }
</script>

<style></style>
