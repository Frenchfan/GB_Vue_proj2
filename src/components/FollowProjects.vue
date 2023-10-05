<script>
import ProjectsList from "@components/ProjectsList.vue";
import {mapStores} from "pinia";
import {useProjectStore} from "@storage/storage.js";

export default {
  name: "FollowProjects",
  components: {ProjectsList},
  computed: {
    ...mapStores(useProjectStore)
  }
};
</script>

<template>
  <section class="projects">
    <div class="projects__container">
      <h2 class="projects__title">Follow Our Projects</h2>
      <p class="projects__text">It is a long established fact that a reader will be distracted by the of readable
        content of page lookings at its layouts points.</p>

      <ProjectsList :projects="projectStore.getRandomProjects(4)" target="home"/>

    </div>
  </section>

</template>


<style scoped lang="scss">
.projects {
  @extend %section;

  &__container {
    @extend %container;
  }
  &__title {
    @extend %heading1;
    color: $primary2;
    text-align: center;
    margin-bottom: 10px;
  }
  &__text {
    margin: 0 auto;
    max-width: 740px;
    @extend %paragraphLarge;
    color: $secondary1;
    text-align: center;
    margin-bottom: 93px;
  }
}
</style>
