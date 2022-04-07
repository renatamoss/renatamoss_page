<template>
  <div class="main-template">
    <AppHeader />
    <AppMain />
    <AppFooter />
  </div>
</template>


<script>
import AppHeader from "./section/AppHeader.vue";
import AppMain from "./section/AppMain.vue";
import AppFooter from "./section/AppFooter.vue";

export default {
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
};
</script>