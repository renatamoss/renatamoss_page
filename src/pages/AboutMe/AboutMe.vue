<template>
  <div class="aboutme" id="aboutme">
    <Title title="Sobre Mim" subtitle="Olá!" subtitle-class="subtitleAboutme" />
    <div class="aboutme__container">
      <div class="aboutme__box">
        <p>
          Com formação voltada para o mundo dos negócios & relacionamentos, há
          um ano atrás escolhi transacionar minha carreira para o universo da
          tecnologia.
        </p>
        <p>
          Durante a minha experiência profissional já fiz muitas coisas que não
          estavam ligadas à criatividade, mas que contribuíram muito para que eu
          seja quem sou hoje.
        </p>
        <p>
          Em minha jornada tech concluí trilhas de formação de Front-End e
          atualmente estou desenvolvendo com Vue Js, HTML, CSS, SASS, Javascript
          e Bootstrap. Também já desenvolvi projetos pessoais com conhecimentos
          básicos em PHP, SQL e MySQL.
        </p>
        <p>
          Sou uma pessoa simples e que acredita muito no lado positivo das
          coisas! Fique à vontade para me adicionar em minhas redes sociais.
        </p>
      </div>
      <Images
        className="image__default image__default--photo-renata"
        fileName="renata-photo.jpg"
        descriptionImage="Renata photo"
      />
    </div>
  </div>
</template>


<script>
import Title from "@/components/shared/Title/Title.vue";
import Images from "../../components/shared/Images/Images.vue";

export default {
  components: {
    Title,
    Images,
  },
};
</script>


<style lang="scss" scoped>
.aboutme {
  background-color: var(--bg-color-5);
  height: 100vh;
  width: 100%;
  z-index: 1;

  &__container {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;

    margin: auto;
    width: 60%;

    .aboutme__box {
      display: flex;
      flex-direction: column;
      align-items: center;
      height: auto;
      width: 70%;

      p {
        font-size: 1rem;
        margin: 1rem 0;
        text-align: right;
      }
    }
  }
}

@media (max-width: 1200px) {
  .aboutme__container {
    width: 90%;
  }
}

@media (max-width: 992px) {
  .aboutme {
    height: 100%;
    padding: 0;

    .aboutme__container {
      border-radius: 0;
      flex-direction: column;
      justify-content: center;
      width: 100%;

      .aboutme__box {
        padding: 1rem 0.5rem 0 0.5rem;

        p {
          text-align: left;
        }
      }
    }
  }
}
</style>