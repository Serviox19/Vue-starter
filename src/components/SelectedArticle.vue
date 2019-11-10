<template>
  <div v-if="selected">
    <h3>{{ selected.title }}</h3>
  </div>
</template>

<script>
  export default {
    name: 'SelectedArticle',
    props: ['selected']
  }
</script>

<style scoped>

</style>
