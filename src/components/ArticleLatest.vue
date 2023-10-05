<script>
import CardActions from "@components/CardActions.vue";
import {router} from "@routes/routes.js";

export default {
  name: "ArticleLatest",
  components: {CardActions},
  props: {
    article: {
      img: String,
      tag: String,
      title: String,
      description: String,
      id: Number | String,
      date: String,
    }
  },
  methods: {
    navigate() {
      router.push({path: `/blog/${this.article.id}`});
    }
  }
};
</script>

<template>
  <div class="article">
    <div class="article__image">
      <img :src="article.img"
           :alt="article.tag"
           class="article__img">
    </div>
    <div class="article__box">
      <h3 class="article__title">{{ article.title }}</h3>
      <p class="article__text">{{ article.description }}</p>
      <CardActions :date="article.date" :action="navigate"/>
    </div>
  </div>
</template>

<style scoped
       lang="scss">

.article {
  @include rounded(62px);
  padding: 22px;
  display: flex;
  gap: 65px;
  border: 1px solid #E7E7E7;
  box-shadow: 0 10px 30px 0 rgba(255, 255, 255, 0.25);
  &__image {
    max-width: 570px;
    width: 100%;
    img {
      width: 100%;
      object-fit: cover;
      border-radius: 50px;
    }
  }
  &__box {
    padding-top: 51px;
  }
  &__title {
    @extend %heading3;
    color: $primary2;
    margin-bottom: 22px;
    max-width: 470px;
  }
  &__text {
    @extend %paragraphLarge;
    color: $secondary1;
    margin-bottom: 41px;
    max-width: 470px;
  }
}
</style>
