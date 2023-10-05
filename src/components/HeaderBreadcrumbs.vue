<script>
export default {
  name: "HeaderBreadcrumbs",
  computed: {
    direction() {
      return this.$route.path;
    }
  }
};
</script>

<template>
  <nav class="nav">
    <router-link class="nav__link" to="/">Home</router-link>
    /
    <router-link class="nav__link" :to="direction">{{direction.slice(1)[0].toUpperCase() + direction.slice(2)}}</router-link>
  </nav>
</template>

<style scoped lang="scss">
.nav {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  @extend %paragraphLarge;

  &__link {
    @extend %paragraphLarge;
    @include linkColor($secondary1,$primary1);
    text-decoration: none;
  }
}

</style>
