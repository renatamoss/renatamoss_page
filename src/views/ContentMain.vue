<template>
  <div class="main__container">
    <Home />
    <Projects />
    <BannerPage />
  </div>
</template>


<script>
import Home from "@/pages/Home/Home.vue";
import Projects from "@/pages/Projects/Projects.vue";
import BannerPage from "@/components/objects/BannerPage/BannerPage.vue";

export default {
  components: {
    Home,
    Projects,
    BannerPage,
  },
};
</script>





