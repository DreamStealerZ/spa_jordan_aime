<template>
  <div class="main d-flex justify-content-center">
    <div id="app w-100">
      <h1 class="text-center">Liste des articles</h1>
      <table class="table bg-light px-5">
        <tbody>
          <tr v-for="(article, index) in articles" :id="article.id" :key="index">
            <td v-text="article.title" class="vignette"></td>
            <td v-text="article.title" class="titre"></td>
            <td><router-link :to="'article/'+article.id">Voir L'article</router-link></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      articles: []
    }

  },
  methods: {
    getArticle() {
      const URL = "https://jsonplaceholder.typicode.com/posts"
      axios
        .get(URL)
        .then(res => {
          this.articles = res.data;
        })
    }
  },
  mounted() {
    this.getArticle();
  }
}
</script>

<style>
#app{
  margin-top: 0px !important;
}


</style>