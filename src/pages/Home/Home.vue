<template>
  <div class="home" id="home">
    <div class="home__container">
      <div class="home__box-image">
        <transition name="fade-image">
          <Images
            v-show="showHome"
            className="image__default image__default--home"
            :class="{ scroll__image }"
            fileName="image-home-woman.png"
            descriptionImage="Woman sitting on chair"
          />
        </transition>
      </div>
      <div class="home__box-banner">
        <BannerHome />
        <transition name="fade-button">
          <Button
            v-show="showHome"
            className="button__item button__item--aboutme"
            href="#aboutme"
            title="Sobre Mim"
            target="_self"
            symbol="bi bi-plus-circle-fill"
          />
        </transition>
        <transition name="fade-button">
          <Button
            v-show="showHome"
            className="button__item button__item--projects"
            href="#projects"
            title="Conheça Meus Projetos"
            target="_self"
            symbol="bi bi-plus-circle-fill"
          />
        </transition>
      </div>
    </div>
  </div>
</template>


<script>
import Images from "../../components/shared/Images/Images.vue";
import BannerHome from "../../components/objects/BannerHome/BannerHome.vue";
import Button from "../../components/shared/Button/Button.vue";

export default {
  components: {
    Images,
    BannerHome,
    Button,
  },
  data() {
    return {
      showHome: false,
      scroll__image: false,
    };
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 500) {
        this.scroll__image = false;
        console.log("desceu");
      } else if (window.scrollY < 300) {
        this.scroll__image = true;
      }
    },
  },
  mounted() {
    this.showHome = true;
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    this.showHome = false;
  },
};
</script>


<style lang="scss" scoped>
.home {
  background-color: var(--bg-color-4);
  height: 100vh;
  padding: 10rem 0 2rem 0;
  position: relative;
  width: 100%;
  z-index: 2;

  .scroll__image {
    transform: scale(1.2);
    transition: 0.4s ease-in;
  }

  &__container {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;

    height: 100%;
    margin: auto;
    padding: 2rem 0;
    width: 60%;

    .home__box-banner {
      display: flex;
      flex-direction: column;
      align-items: center;
      height: auto;
      text-align: center;
      width: auto;
    }
  }
}

@media (max-width: 1200px) {
  .home__container {
    width: 90%;
  }
}

@media (max-width: 992px) {
  .home {
    padding: 0;
    height: 85vh;

    .home__container {
      border-radius: 0;
      flex-direction: column;
      justify-content: center;
      width: 100%;

      .home__box-image {
        height: 225px;
      }

      .home__box-banner {
        padding-top: 1rem;
      }
    }
  }
}

/*max-height*/
@media screen and (max-height: 500px) {
  .home {
    height: 100%;
  }
}

/*transition image */
@keyframes image-come-down {
  0% {
    opacity: 0;
    transform: translateY(-10rem);
  }
  95% {
    opacity: 0.9;
  }
  100% {
    opacity: 1;
    transform: translateY(0) easy;
  }
}
.fade-image-enter,
.fade-image-enter-active {
  animation: image-come-down ease-in 1s;
}

/*transition button */
@keyframes button-come-down {
  0% {
    opacity: 0;
    transform: translateX(10rem);
  }
  95% {
    opacity: 0.9;
  }
  100% {
    opacity: 1;
    transform: translateX(0) easy;
  }
}
.fade-button-enter,
.fade-button-enter-active {
  animation: button-come-down ease-in 1s;
}
</style>