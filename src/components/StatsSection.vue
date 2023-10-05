<script>
export default {
  name: "StatsSection"
};
</script>

<template>
  <section class="stats">
    <div class="stats__bg">
      <div class="stats__container">
        <div class="stats__item">
          <h2 class="stats__title">12</h2>
          <p class="stats__text">Years of Experience</p>
        </div>
        <div class="stats__divider"></div>
        <div class="stats__item">
          <h2 class="stats__title">85</h2>
          <p class="stats__text">Success projects</p>
        </div>
        <div class="stats__divider"></div>
        <div class="stats__item">
          <h2 class="stats__title">15</h2>
          <p class="stats__text">Active Projects</p>
        </div>
        <div class="stats__divider"></div>
        <div class="stats__item">
          <h2 class="stats__title">95</h2>
          <p class="stats__text">Happy Customers</p>
        </div>
      </div>
    </div>
  </section>
</template>


<style scoped lang="scss">

.stats {
  @extend %section;
  &__bg {
    background-color: $primary3;
  }

  &__container {
    @extend %container;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    padding: 150px 0;
  }
  &__divider {
    height: 130px;
    border-right: 1px solid $primary1;
  }
  &__title {
    @extend %statsTitle;
    margin-bottom: 16px;
    color: $primary1;
    text-align: center;
  }
  &__text {
    @extend %paragraphLarge;
    color: $secondary1;
    text-align: center;
  }
}
</style>
