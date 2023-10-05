<script>
import InternoHeader from "@/components/InternoHeader.vue";
import InternoFooter from "@/components/InternoFooter.vue";
export default {
  name: 'App',
  components: {InternoHeader, InternoFooter}
}
</script>

<template>
  <div class="pages">
    <InternoHeader />
    <div class="pages__view">
      <router-view></router-view>
    </div>
    <InternoFooter />
  </div>
</template>

<style scoped lang="scss">
.pages {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  &__view {
    flex-grow: 1;
  }
}
</style>
