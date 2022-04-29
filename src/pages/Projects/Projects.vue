<template>
  <div class="projects" id="projects">
    <Title
      title="Meus Projetos"
      subtitle="O que estou estudando?"
      subtitleClass="subtitleProjects"
    />
    <ProjectsGroup />
  </div>
</template>


<script>
import Title from "@/components/shared/Title/Title.vue";
import ProjectsGroup from "./ProjectsGroup.vue";

export default {
  components: {
    Title,
    ProjectsGroup,
  },
};
</script>


<style lang="scss" scoped>
.projects {
  height: auto;
  position: relative;
  width: 100%;
  z-index: 1;

  margin-top: -5rem;
  padding: 3rem 0;

  &__back-desktop {
    display: flex;
    justify-content: right;

    bottom: 0;
    margin-right: 20%;
    padding-bottom: 4rem;
    position: fixed;
    right: 0;
    z-index: 9999;
  }
}
@media (max-width: 1200px) {
  .projects__back-desktop {
    margin-right: 5%;
  }
}

@media (max-width: 992px) {
  .projects {
    margin-top: 0;
    padding: 0;
  }
}
</style>