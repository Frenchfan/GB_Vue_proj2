<script>
import ArticlesCard from "@components/ArticlesCard.vue";

export default {
  name: "ArticlesList",
  components: {ArticlesCard},
  props: {
    articles: Array,
    latest: Function,
  },
  methods: {
    makeLatest(idx) {
      if (this.latest) {
        this.latest(idx);
      }
    }
  }
};
</script>

<template>
  <div class="cards">

    <ArticlesCard v-for="article in articles"
                  @click="makeLatest(article.id)"
                  :id="article.id"
                  :title="article.title"
                  :img="article.img"
                  :date="article.date"
                  :tag="article.tag"
                  :key="article.id"/>

  </div>
</template>


<style scoped lang="scss">
.cards {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  row-gap: 30px;
}
</style>
