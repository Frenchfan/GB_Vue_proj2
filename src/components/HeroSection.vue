<script>
import {router} from "@routes/routes.js";

export default {
  name: "HeroSection",
  methods: {
    navigate() {
      router.push({path: '/project'})
    }
  }
};
</script>

<template>
  <section class="hero">
    <div class="hero__container">
      <div class="hero__intro">
        <h1 class="hero__title">Let Your Home
          Be Unique</h1>
        <p class="hero__text">There are many variations of the passages of
          lorem Ipsum fromavailable, majority.</p>
        <button class="hero__btn" @click="navigate">Get Started
          <svg xmlns="http://www.w3.org/2000/svg"
               width="19"
               height="17"
               viewBox="0 0 19 17"
               fill="none">
            <path d="M2 8.43542L15.7232 8.29857M10.6182 1.91138L17.1412 8.43436L10.4868 15.0887"
                  stroke="#CDA274"
                  stroke-width="2"
                  stroke-linecap="square"
                  stroke-linejoin="round"/>
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.hero {
  @extend %section;

  &__container {
    @include rounded(50px);
    @extend %container;
    min-height: 75vh;
    padding: 50px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    background-image: url('@assets/img/hero/Image.png');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  &__intro {
    max-width: 450px;
  }
  &__title {
    @extend %heroTitle;
    color: $primary2;
    margin-bottom: 18px;
  }
  &__text {
    @extend %paragraphLarge;
    color: $secondary1;
    margin-bottom: 21px;
  }
  &__btn {
    @extend %btn;
    @include btnColors($primary2, $primary1);
    @extend %btnText;
    color: #ffffff;
  }
}
</style>
