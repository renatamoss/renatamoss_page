<template>
  <div class="title__box">
    <h2 class="title">{{ title }}</h2>
    <h3 class="subtitle">{{ subtitle }}</h3>
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
  },
};
</script>


<style lang="scss" scoped>
.title__box {
  height: auto;
  padding-top: 7rem;
  width: 100%;

  .title {
    color: var(--title-color-3);
    font-size: var(--font-size-3);
    font-weight: bolder;
    margin-top: 2rem;
    text-align: center;
  }

  .subtitle {
    color: var(--title-color-5);
    font-size: 1.2rem;
    font-weight: lighter;
    margin-top: 0.5rem;
    text-align: center;
  }
}

@media (max-width: 992px) {
  .title__box {
    height: auto;
    padding-top: 3rem;
    max-width: 100%;

    .title {
      font-size: var(--font-size-2);
    }
  }
}
</style>