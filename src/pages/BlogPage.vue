<script>
import img1 from '@assets/img/articles/Image1.png';
import img2 from '@assets/img/articles/Image2.png';
import img3 from '@assets/img/articles/Image3.png';
import img4 from '@assets/img/articles/Image4.png';
import img5 from '@assets/img/articles/Image5.png';
import img6 from '@assets/img/articles/Image6.png';
import img7 from '@assets/img/articles/Image7.png';
import ArticlesList from "@components/ArticlesList.vue";
import PaginationButtons from "@components/PaginationButtons.vue";
import ArticleLatest from "@components/ArticleLatest.vue";
import PageHeader from "@components/PageHeader.vue";
import headerImg from "@assets/img/HeaderBackgrounds/BlogPage.png"
export default {
  name: "BlogPage",
  components: {PageHeader, ArticleLatest, PaginationButtons, ArticlesList},
  data() {
    return {
      articles: [
        {
          img: img1,
          tag: 'Kitchan Design',
          title: 'Let’s Get Solution For Building Construction Work',
          date: '26 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 1
        },
        {
          img: img2,
          tag: 'Living Design',
          title: 'Low Cost Latest Invented Interior Designing Ideas.',
          date: '22 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 2
        },
        {
          img: img3,
          tag: 'Interior Design',
          title: 'Best For Any Office & Business Interior Solution',
          date: '25 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 3
        },
        {
          img: img4,
          tag: 'Kitchan Design',
          title: 'Let’s Get Solution For Building Construction Work',
          date: '26 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 4
        },
        {
          img: img5,
          tag: 'Living Design',
          title: 'Low Cost Latest Invented Interior Designing Ideas.',
          date: '22 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 5
        },
        {
          img: img6,
          tag: 'Interior Design',
          title: 'Best For Any Office & Business Interior Solution',
          date: '25 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 6
        },
        {
          img: img7,
          tag: 'Living Design',
          title: 'Low Cost Latest Invented Interior Designing Ideas.',
          date: '26 December,2022',
          description: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief. Lorem Ipsum is not simply random text. It has roots in a piece of classica.`,
          id: 5
        },
      ],
      currentPage: 1,
      latestIdx: 1,
      headerImage: headerImg,
    }
  },
  methods: {
    setCurrentPage(page) {
      this.currentPage = page;
    },
    setLatestArticle(idx) {
      this.latestIdx = idx;
    }
  },
  computed: {
    totalPages() {
      return Math.ceil((this.articles.length * 2) / 3)
    },
    mockArticles() {
      const mock = [...this.articles, ...this.articles, ...this.articles, ...this.articles];
      let i = 1;
      mock.forEach(el => el.id = i++);
      return mock;
    },
    renderedArticles() {
      return this.mockArticles.slice((this.currentPage - 1) * 6, this.currentPage * 6);
    },
    latestArticle() {
      return this.mockArticles.filter(el => el.id === this.latestIdx)[0] || this.mockArticles[0];
    }
  },
};
</script>

<template>
  <div class="blog">
    <PageHeader title="Articles & News" :image="headerImage" />
    <div class="blog__container">
      <h2 class="blog__title">Latest Post</h2>
      <div class="blog__inner">
        <ArticleLatest :article="latestArticle" />
      </div>
      <h2 class="blog__title">Articles & News</h2>
      <div class="blog__inner">
        <ArticlesList :articles="renderedArticles" :latest="setLatestArticle"/>
      </div>
      <PaginationButtons :total="totalPages" :current="currentPage" :action="setCurrentPage" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.blog {
  margin-bottom: 200px;
  &__container {
    @extend %container;
  }
  &__title {
    margin-bottom: 30px;
    @extend %heading1;
    color: $primary2;
  }
  &__inner {
    &:nth-of-type(1) {
      margin-bottom: 150px;
    }
    &:nth-of-type(2) {
      margin-bottom: 51px;
    }
  }
}
</style>
