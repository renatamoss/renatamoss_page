<template>
  <li class="project__item">
    <!--section Image-->
    <div class="project__painel">
      <Images
        :className="[
          'image__default',
          project.image.verticalAlign === true
            ? 'image__default--vertical'
            : '',
        ]"
        :fileName="'ImagesProjects/' + project.image.fileName"
        :descriptionImage="project.image.title"
      />
    </div>

    <!--section content-->
    <div class="project__content">
      <Content
        :title="project.content.title"
        :subtitle="project.content.subtitle"
        :text="project.content.text"
      />

      <!--section buttons-->
      <div class="project__buttons">
        <Button
          :class="button.github.className"
          :href="
            'https://github.com/renatamoss/' + project.buttons.github.hrefName
          "
          :title="button.github.title"
          :target="button.github.target"
          :symbol="button.github.symbol"
        />
        <Button
          :class="button.preview.className"
          :href="project.buttons.preview.hrefName"
          :title="button.preview.title"
          :target="button.preview.target"
          :symbol="button.preview.symbol"
        />
      </div>
    </div>
  </li>
</template>

<script>
import Images from "../../components/shared/Images/Images.vue";
import Content from "../../components/shared/Content/Content.vue";
import Button from "../../components/shared/Button/Button.vue";
import Icon from "../../components/shared/Icon/Icon.vue";

export default {
  components: {
    Images,
    Content,
    Button,
    Icon,
  },

  props: {
    project: {
      required: true,
      type: Object,
    },
  },

  data() {
    return {
      button: {
        github: {
          className: "button__item button__item--github",
          title: "Github",
          target: "_blank",
          symbol: "bi bi-github",
        },
        preview: {
          className: "button__item button__item--preview",
          title: "Preview",
          target: "_blank",
          symbol: "bi bi-play-circle",
        },
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.project__item {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;

  height: auto;
  margin: 0 auto;
  padding-bottom: 3rem;
  width: 60%;

  .project__painel {
    display: flex;
    justify-content: center;
    align-items: center;

    background-color: var(--bg-color-2);
    border-radius: 0.4rem;
    box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px,
      rgba(60, 64, 67, 0.15) 0px 2px 6px 2px;
    height: 300px;
    min-width: 300px;
    overflow: hidden;
    text-align: center;
  }

  .project__content {
    text-align: left;

    .project__buttons {
      margin: 0 0.5rem;
    }
  }
}

@media (max-width: 1200px) {
  .project__item {
    min-width: 90%;
  }
}

@media (max-width: 992px) {
  .project__item {
    display: block;
    flex-direction: column;
    padding: 0 1rem;
    min-width: 100%;

    .project__content {
      padding-bottom: 4rem;

      .project__buttons {
        display: flex;
        justify-content: center;
      }
    }
  }
}

@media (max-width: 340px) {
  .project__painel {
    min-width: 210px;
  }
}
</style>