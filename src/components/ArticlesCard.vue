<script>
import {router} from "@routes/routes.js";
import CardActions from "@components/CardActions.vue";

export default {
  name: "ArticlesCard",
  components: {CardActions},
  props: {
    img: String,
    tag: String,
    title: String,
    date: String,
    id: Number
  },
  methods: {
    navigate() {
      router.push({path: `/blog/${this.id}`});
    }
  }
};
</script>

<template>
  <div class="card">
    <div class="card__image">
      <img :src="img"
           :alt="tag">
      <button class="card__btn-img">{{ tag }}</button>
    </div>
    <div class="card__description">
      <h3 class="card__title">{{ title }}</h3>
      <CardActions :action="navigate" :date="date" />
    </div>
  </div>
</template>


<style scoped lang="scss">

.card {
  @include rounded(62px);
  max-width: 382px;
  padding: 21px;
  border: 1px solid #E7E7E7;
  box-shadow: 0 10px 30px 0 rgba(255, 255, 255, 0.25);
  transition: color 0.3s ease-in-out, background-color 0.3s ease-in-out;
  &__title {
    @extend %heading3;
    color: $primary2;
  }
  &__text {
    @extend %paragraphXs;
    color: $secondary1;
  }
  &__btn {
    &-img {
      @include rounded(8px 8px 8px 0);
      position: absolute;
      bottom: 20px;
      left: 20px;
      display: block;
      padding: 4px 5px 8px 11px;
      border-color: transparent;
      outline: none;
      background: #FFF;
      color: $secondary1;
      font-size: 16px;
      line-height: 150%;
      cursor: pointer;
      transition: color 0.3s ease-in-out, background-color 0.3s ease-in-out;
    }
  }
  &__image {
    position: relative;
    img {
      @include rounded(45px 45px 0 0);
      max-width: 340px;
      width: 100%;
      object-fit: cover;
    }
  }
  &:hover {
    background-color: $primary3;
  }
}
</style>
