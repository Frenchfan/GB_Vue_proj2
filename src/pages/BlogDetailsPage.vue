<script>
import headerImg from "@assets/img/HeaderBackgrounds/BlogDetails.png";
import PageHeader from "@components/PageHeader.vue";
import BlogTags from "@components/BlogTags.vue";
import BlogDetailsContent from "@components/BlogDetailsContent.vue";

export default {
  name: "BlogDetailsPage",
  components: {BlogDetailsContent, BlogTags, PageHeader},
  data() {
    return {
      headerImage: headerImg,
      tags: ['Kitchen', 'Bedroom', 'Building', 'Architecture', 'Kitchen Planning', 'Bed Room'],
      providedTag: '',
    };
  },
  methods: {
    setProvidedTag(value) {
      if (this.providedTag === value) {
        this.providedTag = '';
      } else {
        this.providedTag = value;
      }
    }
  }
};
</script>


<template>
  <div>
    <PageHeader :image="headerImage"/>
    <div class="blog">
      <div class="blog__container">
        <div class="blog__content">
          <BlogDetailsContent />
        </div>
        <div class="blog__tags">
          <BlogTags :provided-tag="providedTag" :tags="tags" @provide-tag="setProvidedTag"/>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.blog{
  margin-bottom: 96px;
  &__container {
    @extend %container;
    display: flex;
    flex-wrap: wrap-reverse;
    gap: 50px;
  }
  &__content {
    width: clamp(320px, 66% - 25px, 100vw);
  }
  &__tags {
    width: clamp(320px, 33% - 25px, 100vw);
  }
}
</style>
