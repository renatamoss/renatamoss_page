<template>
  <div class="aboutme" id="aboutme">
    <Title title="Sobre Mim" subtitle="Minha Jornada Tech" subtitle-class="subtitleAboutme" />
    <div class="aboutme__container">
      <transition name="fade-aboutme">
        <div class="aboutme__box" v-show="showAboutMe">
          <p>
            Após anos atuando profissionalmente no mundo dos negócios & relacionamentos, eu escolhi
            transacionar minha carreira para o universo da tecnologia.
          </p>
          <p>
            Para mim, a vida só faz sentido quando vivida com o coração. Encontrar o que traz brilho aos olhos, viver
            com propósito, valorizar os momentos cotidianos, buscar formas cada vez mais sustentáveis de se
            realizar, seja como mãe, filha, amiga e profissional. Acredito que quando vivemos com propósito, tudo a
            nossa
            volta passa a ser, naturalmente, mais harmônico.
          </p>
          <p>
            Nesta nova jornada tech, estou em busca de desafios que me permitam ampliar habilidades e aprender
            diferentes tecnologias. Sou uma pessoa simples e que acredita muito no lado positivo das
            coisas! Fique à vontade para me adicionar em minhas redes sociais.
          </p>
        </div>
      </transition>
      <transition name="fade-photo">
        <Images v-show="showAboutMe" className="image__default image__default--photo-renata" fileName="renata-photo.jpg"
          descriptionImage="Renata photo" />
      </transition>
    </div>
    <ButtonBack />
  </div>
</template>


<script>
import Title from "@/components/shared/Title/Title.vue";
import Images from "../../components/shared/Images/Images.vue";
import ButtonBack from "@/components/objects/ButtonBack/ButtonBack.vue";

export default {
  components: {
    Title,
    Images,
    ButtonBack,
  },
  data() {
    return {
      showAboutMe: false,
    };
  },
  methods: {
    handleScroll() {
      this.showAboutMe = true;
    },
  },
  mounted() {
    document.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    document.addEventListener("scroll", this.handleScroll);
  },
};
</script>


<style lang="scss" scoped>
.aboutme {
  background-color: var(--bg-color-5);
  color: var(--secundary-text-color);
  height: 100%;
  width: 100%;
  z-index: 1;

  margin-top: -5rem;
  padding: 3rem 0;

  &__container {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;

    margin: 2rem auto;
    width: 60%;

    .aboutme__box {
      display: flex;
      flex-direction: column;
      align-items: center;

      height: auto;
      width: 50%;

      p {
        font-size: 1rem;
        margin: 0.5rem 0;
        text-align: right;
      }
    }
  }
}

@media (max-width: 1200px) {
  .aboutme {
    &__container {
      width: 90%;
    }
  }
}

@media (max-width: 992px) {
  .aboutme {
    margin-top: 0;
    padding: 0;

    .aboutme__container {
      border-radius: 0;
      flex-direction: column;
      justify-content: center;
      margin: 0 auto;
      padding: 0;
      width: 100%;

      .aboutme__box {
        padding: 1rem 1rem 0 1rem;
        width: 100%;

        p {
          text-align: left;
        }
      }
    }
  }
}

@media (max-width: 576px) {
  .aboutme {
    .aboutme__container {
      .aboutme__box {
        p {
          font-size: 0.9rem;
        }
      }
    }
  }
}

/*transition photo */
@keyframes photo-come-down {
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

.fade-photo-enter,
.fade-photo-enter-active {
  animation: photo-come-down ease-in 1.2s;
}

/*transition aboutme */
@keyframes aboutme-come-down {
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

.fade-aboutme-enter,
.fade-aboutme-enter-active {
  animation: aboutme-come-down ease-in 1.2s;
}
</style>