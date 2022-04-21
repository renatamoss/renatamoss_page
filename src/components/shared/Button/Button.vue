<template>
  <a :class="className" :href="href" :title="title" :target="target">
    {{ title }}
    <Icon :symbol="`${$props.symbol}`" />
  </a>
</template>


<script>
import Icon from "../Icon/Icon.vue";

export default {
  components: {
    Icon,
  },

  props: {
    className: {
      type: String,
    },
    href: {
      type: String,
    },
    title: {
      type: String,
    },
    target: {
      type: String,
    },
    symbol: {
      type: String,
    },
  },
};
</script>


<style lang="scss" scoped>
.button__item {
  display: flex;
  align-items: center;
  justify-content: center;

  background-color: var(--button-bg-color-1);
  color: var(--secundary-text-color);
  border-radius: 0.4rem;
  font-size: 0.8rem;
  font-weight: bolder;
  letter-spacing: 0.1rem;
  margin: 1rem 0.5rem 0 0.5rem;
  text-align: center;
  width: 8rem;
}

.button__item--github,
.button__item--preview {
  padding-left: 0.5rem;
}

.button__item--projects,
.button__item--aboutme {
  font-size: 0.8rem;
  height: 3rem;
  margin-top: 1rem;
  padding-left: 0.5rem;
  width: 18rem;
}

.button__item--aboutme {
  background-color: var(--button-bg-color-6);
}

.button__item--projects {
  background-color: var(--button-bg-color-1);
}

.button__item--allprojects {
  background-color: var(--button-bg-color-3);
  margin: 0 auto 4rem auto;
  padding-left: 0.5rem;
  width: 8rem;
}

.button__item--back {
  background-color: var(--button-bg-color-3);
  height: 3rem;
  width: 8rem;
  opacity: 0.6;
}

@media (min-width: 992px) {
  .button__item--github:hover {
    background-color: var(--button-bg-color-hover-1);
    transform: scale(1.03);
  }

  .button__item--preview:hover {
    background-color: var(--button-bg-color-hover-6);
    transform: scale(1.03);
  }

  .button__item--aboutme:hover,
  .button__item--projects:hover {
    transform: scale(1.03);
  }

  .button__item--allprojects:hover {
    background-color: var(--button-bg-color-hover-6);
    transform: scale(1.03);
  }

  .button__item--back:hover {
    background-color: var(--button-bg-color-hover-3);
    transform: scale(1.1);
  }
}

@media (max-width: 992px) {
  .button__item--aboutme,
  .button__item--projects {
    display: none;
  }
}
</style>