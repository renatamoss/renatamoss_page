<template>
  <ul :class="className">
    <li class="social__links" v-for="(link, index) of LinksList" :key="index">
      <a
        @click="closeDropdown"
        :class="['social__link-item', link.class]"
        :href="link.href"
        :title="link.title"
        target="_blank"
      >
        <Icon :symbol="link.icon" />
      </a>
    </li>
  </ul>
</template>


<script>
import LinksList from "./LinksList.js";
import Icon from "@/components/shared/Icon/Icon.vue";

export default {
  components: {
    Icon,
  },

  props: { className: String },

  data() {
    return {
      LinksList: LinksList,
    };
  },

  methods: {
    closeDropdown(evt) {
      this.$emit("closeDropdown", evt);
    },
  },
};
</script>


<style lang="scss" scoped>
.social__box--line,
.social__box--dropdown {
  display: flex;
  flex-direction: row;
  align-items: center;

  height: 50%;
  padding-left: 0.5rem;

  ul {
    margin: 0;
  }

  .social__link-item {
    display: flex;
    align-items: center;
    justify-content: center;

    background-color: var(--button-bg-color-1);
    box-shadow: rgba(0, 0, 0, 0.25) 0px 0.0625em 0.0625em,
      rgba(0, 0, 0, 0.25) 0px 0.125em 0.5em,
      rgba(255, 255, 255, 0.1) 0px 0px 0px 1px inset;
    border-radius: 0.4rem;
    cursor: pointer;
    font-size: var(--font-size-link);
    height: 2.8rem;
    margin-right: 0.5rem;
    width: 2.8rem;
  }
}

.social__box--dropdown {
  display: block;
  padding-left: 0rem;

  .social__link-item {
    background-color: var(--button-bg-color-1);
    margin-top: 0.5rem;
    margin-right: 0rem;
  }
}

@media (min-width: 992px) {
  .social__link-item--linkedin:hover {
    background-color: var(--button-bg-color-hover-2);
    transform: scale(1.1);
  }

  .social__link-item--github:hover {
    background-color: var(--button-bg-color-hover-1);
    transform: scale(1.1);
  }

  .social__link-item--instagram:hover {
    background-color: var(--button-bg-color-hover-3);
    transform: scale(1.1);
  }

  .social__link-item--twitter:hover {
    background-color: var(--button-bg-color-hover-5);
    transform: scale(1.1);
  }

  .social__link-item--email:hover {
    background-color: var(--button-bg-color-hover-4);
    transform: scale(1.1);
  }
}

@media (max-width: 992px) {
  .social__box--line {
    display: none;
  }
}
</style>