<script>
import img1 from "@assets/img/blog/Photo1.png";
import img2 from "@assets/img/blog/Photo2.png";
import BlogDetailsDivider from "@components/BlogDetailsDivider.vue";

export default {
  name: "BlogDetailsContent",
  components: {BlogDetailsDivider},
  data() {
    return {
      images: {
        top: img1,
        bottom: img2,
      }
    };
  }
};
</script>

<template>
  <div class="content">
    <h2 class="content__title">Let’s Get Solution for Building
      Construction Work</h2>
    <img :src="images.top"
         alt="Image"
         class="content__img">
    <div class="content__stats stats">
      <p class="stats__item">26 December,2022 </p>
      <p class="stats__item">Interior / Home / Decore</p>
    </div>
    <p class="content__text text">Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary
      to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered
      alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.</p>
    <p class="content__text text">Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet
      tend to repeat predefined chunks as necessary.</p>
    <div class="content__divider">
      <BlogDetailsDivider/>
    </div>
    <h2 class="content__title">Design sprints are great</h2>
    <p class="content__text text">Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary
      to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have
      suffered.</p>
    <ol class="content__list">
      <li class="content__item text">Contrary to popular belief.There are many variations of passages of Lorem Ipsum
        available, but the majority have suffered.
      </li>
      <li class="content__item text">Contrary to popular belief.There are many variations of passages of Lorem Ipsum
        available, but the majority have suffered.
      </li>
      <li class="content__item text">Contrary to popular belief.There are many variations of passages of Lorem Ipsum
        available, but the majority have suffered.
      </li>
    </ol>
    <img :src="images.bottom"
         alt="Image"
         class="content__img">
    <p class="content__text text">Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary
      to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have
      suffered.</p>
  </div>
</template>

<style scoped lang="scss">
.content {
  &__title {
    @extend %heading1;
    margin-bottom: 15px;
  }
  &__img {
    max-width: 100%;
    @include rounded(50px);
    margin-bottom: 40px;
  }
  &__text {
    margin-bottom: 24px;
  }
  &__list {
    margin-bottom: 44px;
  }
  &__item {
    list-style-position: inside;
    &::marker {
      color: $primary1;
    }
    &:not(:last-of-type) {
      margin-bottom: 32px;
    }
  }
  &__divider {
    margin-bottom: 27px;
  }
  &__stats {
    margin-bottom: 48px;
  }
}
.text {
  @extend %paragraphLarge;
  color: $secondary1;
  text-align: justify;
}
.stats {
  display: flex;
  justify-content: space-between;
  align-items: center;
  &__item {
    @extend %paragraphXs;
    color: $secondary1;
    padding-right: 50px;
  }
}
</style>
