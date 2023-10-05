<script>
import ArticlesList from "@components/ArticlesList.vue";

export default {
  name: "HomeArticles",
  components: {ArticlesList},
  data() {
    return {
      articles: [
        {
          img: 'src/assets/img/articles/Image1.png',
          tag: 'Kitchan Design',
          title: 'Let’s Get Solution For Building Construction Work',
          date: '26 December,2022',
          id: 1
        },
        {
          img: 'src/assets/img/articles/Image2.png',
          tag: 'Living Design',
          title: 'Low Cost Latest Invented Interior Designing Ideas.',
          date: '22 December,2022',
          id: 2
        },
        {
          img: 'src/assets/img/articles/Image3.png',
          tag: 'Interior Design',
          title: 'Best For Any Office & Business Interior Solution',
          date: '25 December,2022',
          id: 3
        },
      ]
    }
  }
};
</script>

<template>
  <section class="articles">
    <div class="articles__container">
      <h2 class="articles__title">Articles & News</h2>
      <p class="articles__text">
        It is a long established fact that a reader will be distracted by the of readable content of a page when
        lookings at its layouts the points of using.
      </p>
      <ArticlesList :articles="articles" />
    </div>
  </section>
</template>


<style scoped lang="scss">

.articles {
  @extend %section;

  &__container {
    @extend %container;
  }

  &__title {
    @extend %heading1;
    color: $primary2;
    text-align: center;
  }
  &__text {
    @extend %paragraphLarge;
    margin: 0 auto;
    max-width: 740px;
    color: $secondary1;
    text-align: center;
    margin-bottom: 52px;
  }
}
</style>
