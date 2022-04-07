<template>
  <div class="app">
    <DefaultTemplate />
  </div>
</template>


<script>
import DefaultTemplate from "./templates/DefaultTemplate.vue";

export default {
  components: {
    DefaultTemplate,
  },
};
</script>


<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Righteous&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap");

@import "@/style/main.scss";
@import "@/style/_variables.scss";
@import "@/style/_reset.scss";

</style>
