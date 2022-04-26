<template>
  <div class="aboutme" id="aboutme">
    <Title
      title="Sobre Mim"
      subtitle="Minha trajetória como Dev"
      subtitle-class="subtitleAboutme"
    />
    <div class="aboutme__container">
      <div class="aboutme__box">
        <p>
          Com formação voltada para o mundo dos negócios & relacionamentos, há
          um ano atrás escolhi transacionar minha carreira para o universo da
          tecnologia.
        </p>
        <p>
          Em minha jornada tech, concluí trilhas de formação de Front-End, e
          atualmente estou desenvolvendo com Vue Js, HTML, CSS, SASS, JavaScript
          e Bootstrap.
        </p>
        <p>
          Também tenho estudado algumas tecnologias como Gimp, Figma, Heroku e
          Vercel. E já desenvolvi projetos pessoais com PHP, SQL e MySQL.
        </p>
        <p>
          Estou trabalhando na construção do meu portfólio, estando sempre em
          busca de novos desafios, que me permitam ampliar habilidades e aprender
          diferentes tecnologias.
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
};
</script>


<style lang="scss" scoped>
.aboutme {
  background-color: var(--bg-color-5);
  color: var(--secundary-text-color);
  height: 100%;
  width: 100%;
  z-index: 1;

  margin-top: -8rem;
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
</style>