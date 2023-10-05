<script>
import HeroSection from "@components/HeroSection.vue";
import FollowProjects from "@components/FollowProjects.vue";
import StatsSection from "@components/StatsSection.vue";
import HomeArticles from "@components/HomeArticles.vue";

export default {
  name: "HomePage",
  components: {HomeArticles, StatsSection, FollowProjects, HeroSection}
};
</script>

<template>
  <div class="home">
    <HeroSection />
    <FollowProjects />
    <StatsSection />
    <HomeArticles />
  </div>
</template>


<style scoped>

</style>
