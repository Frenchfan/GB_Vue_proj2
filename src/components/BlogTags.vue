<script>
export default {
  name: "BlogTags",
  props: {
    tags: Array,
    providedTag: String,
  },
  emits: ["provide-tag"]
};
</script>

<template>
  <div class="tags">
    <h3 class="tags__title">Tags</h3>
    <div class="tags__actions">
      <button class="tags__btn"
              :class="{active: tag === providedTag}"
              v-for="tag in tags"
              @click="$emit('provide-tag', tag)">{{ tag }}
      </button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.tags {
  width: 100%;
  &__title {
    @extend %heading3;
    margin-bottom: 24px;
    color: $primary2;
  }
  &__actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  &__btn {
    @include btnColors($primary3, $primary1);
    @extend %paragraphSmall;
    display: inline-block;
    padding: 9px 30px;
    border-radius: 10px;
    color: $primary2;
    border: none;
    outline: none;
    transition: background-color 0.2s ease-in-out, color 0.2s ease-in-out;
    cursor: pointer;
  }
}
.active {
  @include btnColors($primary2, $primary1);
  color: #FFFFFF;
}
</style>
