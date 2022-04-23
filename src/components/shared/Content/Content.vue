<template>
  <div class="content__box">
    <h4 class="content__title">
      {{ title }}
    </h4>
    <h4 class="content__subtitle">
      {{ subtitle }}
    </h4>
    <p class="content__text">
      {{ text }}
    </p>
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
    text: {
      type: String,
    },
  },
};
</script>


<style lang="scss" scoped>
.content__box {
  color: var(--primary-text-color);
  font-size: var(--fontsize-default);
  height: 100%;
  padding: 0 1rem;
  width: 100%;

  .content__title {
    color: var(--third-text-color);
    font-weight: bolder;
  }

  .content__subtitle {
    font-style: italic;
    margin-bottom: 1rem;
  }

  .content__text {
    width: 100%;
  }
}

@media (max-width: 992px) {
  .content__box {
    margin-top: 1rem;
    padding: 0;
    max-width: 100%;
  }
}

@media (max-width: 576px) {
  .content__box {
    .content__title {
      font-size: 0.9rem;
    }
    .content__subtitle {
      font-size: 0.9rem;
    }
    .content__text {
      font-size: 0.9rem;
    }
  }
}
</style>