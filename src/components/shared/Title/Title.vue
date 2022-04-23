<template>
  <div class="title__box">
    <h2 class="title">{{ title }}</h2>
    <h3 :class="subtitleClass">{{ subtitle }}</h3>
  </div>
</template>


<script>
export default {
  props: {
    title: {
      type: String,
    },
    subtitle: {
      type: String,
    },
    subtitleClass: {
      type: String,
    },
  },
};
</script>


<style lang="scss" scoped>
.title__box {
  height: auto;
  padding-top: 8rem;
  width: 100%;

  .title {
    color: var(--title-color-6);
    font-size: 1.4rem;
    font-weight: bold;
    margin-top: 2rem;
    text-align: center;
  }

  .subtitleAboutme,
  .subtitleProjects {
    font-size: 1.2rem;
    font-weight: bolder;
    margin-top: 0.5rem;
    text-align: center;
  }

  .subtitleAboutme {
    color: var(--title-color-2);
  }
}

.subtitleProjects {
  color: var(--title-color-5);
}

@media (max-width: 992px) {
  .title__box {
    height: auto;
    padding-top: 1rem;
    max-width: 100%;
  }
}

@media (max-width: 576px) {
  .title__box {
    .title {
      font-size: 1.2rem;
    }

    .subtitleAboutme,
    .subtitleProjects {
      font-size: 1rem;
    }
  }
}
</style>