<script>
export default {
  name: "BlogDetailsDivider"
};
</script>

<template>
  <div class="divider">
    <h2 class="divider__title">"</h2>
    <p class="divider__text">The details are not the details.
      They make the design.</p>
  </div>
</template>

<style scoped lang="scss">
.divider {
  @include rounded(50px);
  padding: 53px;
  text-align: center;
  background-color: $primary3;
  color: $primary1;
  &__title {
    @extend %mark;
  }
  &__text {
    @extend %paragraphItalic;
    margin: 0 auto;
    max-width: 350px;
  }
}
</style>
