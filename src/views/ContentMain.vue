<template>
  <div class="main__container">
    <Home />
    <AboutMe />
    <Projects />
    <BannerPage />
  </div>
</template>


<script>
import Home from "@/pages/Home/Home.vue";
import AboutMe from "@/pages/AboutMe/AboutMe.vue";
import Projects from "@/pages/Projects/Projects.vue";
import BannerPage from "@/components/objects/BannerPage/BannerPage.vue";

export default {
  components: {
    Home,
    AboutMe,
    Projects,
    BannerPage,
  },
};
</script>





