<script>
import HeaderBreadcrumbs from "@components/HeaderBreadcrumbs.vue";

export default {
  name: "PageHeader",
  components: {HeaderBreadcrumbs},
  props: {
    title: String,
    image: String,
  },
};
</script>

<template>
  <div class="header" v-bind:style="{ backgroundImage: 'url(' + image + ')' }">
    <div class="header__container">
      <div class="header__box" v-if="title">
        <h1 class="header__title">{{title}}</h1>
        <HeaderBreadcrumbs />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">

.header {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  height: 356px;
  margin-bottom: 200px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  &__box {
    background-color: #fff;
    padding: 41px 125px;
    border-radius: 37px 37px 0 0;
  }
  &__title {
    @extend %heading1;
    color: $primary2;
  }
}
</style>
