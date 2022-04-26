<template>
  <div class="banner_page">
    <Images
      className="image__default image__default--banner-page"
      fileName="image-banner-page.png"
      descriptionImage="Banner Of Page"
    />
  </div>
</template>


<script>
import Images from "@/components/shared/Images/Images.vue";

export default {
  components: {
    Images,
  },
};
</script>

<style lang="scss" >
.banner_page {
  height: 100%;
  padding: 4rem 0;
  margin: auto;
  width: 60%;
}

@media (max-width: 1200px) {
  .banner_page {
    padding: 1rem 0 4rem 0;
    width: 90%;
  }
}

@media (max-width: 992px) {
  .banner_page {
    padding: 1rem 1rem 4rem 1rem;
    width: 100%;
  }
}

@media (max-width: 576px) {
  .banner_page {
    padding: 0 1rem 1rem 1rem;
    width: 100%;
  }
}
</style>