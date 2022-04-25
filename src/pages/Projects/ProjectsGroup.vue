<template>
  <div class="project__container">
    <Search @searching="searching" />
    <p
      class="project__total"
      v-if="projectsSearch.length === projectsList.length"
    >
      Total de {{ projectsSearch.length }} projetos.
    </p>
    <p class="project__total" v-else-if="projectsSearch.length === 0">
      Nenhum projeto encontrado com "{{ search.toUpperCase() }} ".
    </p>
    <p class="project__total" v-else-if="projectsSearch.length === 1">
      Total de UM projeto com "{{ search.toUpperCase() }} ".
    </p>
    <p class="project__total" v-else>
      Total de {{ projectsSearch.length }} projetos com "{{
        search.toUpperCase()
      }}
      ".
    </p>
    <Button
      @click="Allprojects()"
      className="button__item button__item--allprojects"
      href="#projects"
      title="Todos"
      symbol="bi bi-arrow-counterclockwise"
    />
    <ul class="projects__box">
      <ProjectItem
        v-for="(project, index) of projectsSearch"
        :project="project"
        :key="index"
      />
    </ul>
  </div>
</template>


<script>
import Search from "../../components/objects/Search/Search.vue";
import Button from "../../components/shared/Button/Button.vue";
import ProjectItem from "./ProjectItem.vue";
import projectList from "./ProjectsList.js";

export default {
  components: {
    Search,
    Button,
    ProjectItem,
  },

  data() {
    return {
      projectsList: projectList,
      search: "",
    };
  },

  computed: {
    projectsSearch() {
      if (this.search) {
        // create an expression with search value, trim: exclude spaces/ i: insensitive
        let exp = new RegExp(this.search.trim(), "i");

        // return just the projects that match the search
        let result = this.projectsList.filter((project) =>
          exp.test([
            project.content.title,
            project.content.subtitle,
            project.content.text,
          ])
        );

        return result;
      } else {
        return this.projectsList;
      }
    },
  },

  methods: {
    searching(search) {
      this.search = search;
    },
    Allprojects() {
      this.search = "";
    },
  },
};
</script>


<style lang="scss" scoped>
.project__container {
  background-color: var(--bg-color-4);
  text-align: center;
  width: 100%;

  .project__total {
    color: var(--third-text-color);
    font-size: 1rem;
    font-weight: bold;
    padding: 0.5rem 1rem 1rem 1rem;
  }
}

@media (max-width: 576px) {
  .project__container {
    .project__total {
      font-size: 0.9rem;
    }
  }
}
</style>