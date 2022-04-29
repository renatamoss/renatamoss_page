<template>
  <div class="banner_page">
    <transition name="fade-banner__page">
      <Images
        v-show="showBannerPage"
        className="image__default image__default--banner-page"
        fileName="image-banner-page.png"
        descriptionImage="Banner Of Page"
      />
    </transition>
  </div>
</template>


<script>
import Images from "@/components/shared/Images/Images.vue";

export default {
  components: {
    Images,
  },
  data() {
    return {
      showBannerPage: false,
    };
  },
  methods: {
    isScrolledIntoView(el) {
      let rect = el.getBoundingClientRect();
      let elemTop = rect.top;
      let elemBottom = rect.bottom;

      let isVisible = elemTop < window.innerHeight && elemBottom >= 0;
      return isVisible;
    },
    scroll() {
      window.onscroll = () => {
        let scrolledTo = document.querySelector(".banner_page");

        if (scrolledTo && this.isScrolledIntoView(scrolledTo)) {
          this.showBannerPage = true;
        }
      };
    },
  },
  mounted() {
    this.scroll();
  },
  beforeUnmount() {
    this.showBannerPage = false;
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

/*transition banner__page */
@keyframes banner__page-come-down {
  0% {
    opacity: 0;
    transform: translateX(-10rem);
  }
  95% {
    opacity: 0.9;
  }
  100% {
    opacity: 1;
    transform: translateX(0) easy;
  }
}
.fade-banner__page-enter,
.fade-banner__page-enter-active {
  animation: banner__page-come-down ease-in 1s;
}
</style>