<template>
  <div class="projects" id="projects">
    <Title title="Projetos" subtitle="O que estou desenvolvendo?" />
    <ProjectsGroup />
    <div class="projects__back-desktop">
      <Button
        class="button__item button__item--back"
        href="#home"
        title="Voltar"
        symbol="bi bi-arrow-up-circle-fill"
      />
    </div>
  </div>
</template>


<script>
import Title from "@/components/shared/Title/Title.vue";
import ProjectsGroup from "./ProjectsGroup.vue";
import Button from "@/components/shared/Button/Button.vue";

export default {
  components: {
    Title,
    ProjectsGroup,
    Button,
  },
};
</script>


<style lang="scss" scoped>
.projects {
  height: auto;
  position: relative;
  width: 100%;
  z-index: 1;

  .projects__back-desktop {
    display: flex;
    justify-content: right;

    bottom: 0;
    margin-right: 20%;
    padding-bottom: 4rem;
    position: fixed;
    right: 0;
    z-index: 9999;
  }

  @media (max-width: 1200px) {
    .projects__back-desktop {
      margin-right: 5%;
    }
  }

  @media (max-width: 992px) {
    .projects__back-desktop {
      display: none;
    }
  }
}
</style>