<template>
  <div class="home" id="home">
    <div class="home__container">
      <Images
        className="image__default image__default--home-study"
        fileName="image-home-study.png"
        descriptionImage="Woman sitting on chair"
      />
      <div class="home__box">
        <BannerHome />
        <Button
          className="button__item button__item--aboutme"
          href="#aboutme"
          title="Sobre Mim"
          target="_self"
          symbol="bi bi-plus-circle-fill"
        />
        <Button
          className="button__item button__item--projects"
          href="#projects"
          title="Conheça Meus Projetos"
          target="_self"
          symbol="bi bi-plus-circle-fill"
        />
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
};
</script>


<style lang="scss" scoped>
.home {
  background-color: var(--bg-color-4);
  height: 100vh;
  padding: 10rem 0 2rem 0;
  position: relative;
  width: 100%;
  z-index: 2; //esconder o button back desktop

  &__container {
    background-color: var(--bg-color-2);
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;

    height: 100%;
    margin: auto;
    padding: 2rem 0;
    width: 60%;

    .home__box {
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

      .home__box {
        padding-top: 1rem;
      }
    }
  }
}

/*max-height*/
@media screen and (max-height: 700px) {
  .home {
    height: 100%;
  }
}
</style>