<template>
  <div class="notFound">
    <div class="notFound__container">
      <div class="notFound__info">
        <h1 class="notFound__title">404</h1>
        <p class="notFound__text">We are sorry, but the page
          you requested was not found</p>
        <button class="notFound__btn"
                @click="navigate">Back To Home
          <svg width="29"
               height="30"
               viewBox="0 0 29 30"
               fill="none"
               xmlns="http://www.w3.org/2000/svg">
            <path d="M6.58984 14.9353L20.313 14.7984M15.208 8.41125L21.731 14.9342L15.0766 21.5886"
                  stroke="#292F36"
                  stroke-width="2"
                  stroke-linecap="square"
                  stroke-linejoin="round"/>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import {router} from "@routes/routes.js";

export default {
  name: "NotFoundPage",
  methods: {
    navigate() {
      router.push({path: "/"});
    }
  }
};
</script>

<style scoped
       lang="scss">

.notFound {
  min-height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-image: url('@assets/img/NotFound/Images.png');
  background-repeat: no-repeat;
  background-position: top right;
  background-size: contain;

  &__container {
    @extend %container;
    width: 100%;
  }

  &__info {
    max-width: 570px;
  }

  &__title {
    @extend %grand;
    color: $primary1;
    margin-bottom: 15px;
  }

  &__text {
    @extend %heading2;
    color: $primary2;
    margin-bottom: 23px;
  }

  &__btn {
    @extend %btn;
    @include btnColors($primary2, $primary1);
    @extend %btnText;
    color: #ffffff;
  }
}
</style>
