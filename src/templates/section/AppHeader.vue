<template>
  <nav class="header" :class="{ header_collor }" id="header">
    <div class="header__container">
      <TitleHeader />

      <!--min-widht: 992px -->
      <LinksLine />

      <!--max-widht: 992px -->
      <Dropdown />
    </div>
  </nav>
</template>


<script>
import TitleHeader from "@/components/objects/TitleHeader/TitleHeader.vue";
import LinksLine from "@/components/objects/LinksMenu/LinksLine/LinksLine.vue";
import Dropdown from "@/components/objects/LinksMenu/Dropdown/Dropdown.vue";

export default {
  components: {
    TitleHeader,
    LinksLine,
    Dropdown,
  },
  data() {
    return {
      showAboutMe: false,
      header_collor: false,
    };
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 300) {
        this.header_collor = true;
      } else if (window.scrollY < 300) {
        this.header_collor = false;
      }
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.addEventListener("scroll", this.handleScroll);
  },
};
</script>



<style lang="scss" scoped>
.header_collor {
  background-color: rgba(38, 58, 109, 0.8) !important;
  height: 5rem !important;
  transition: 0.4s ease-in;
}

.header {
  background-color: var(--bg-color-1);
  box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px,
    rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
  height: 8rem;
  position: fixed;
  width: 100%;
  z-index: 3;
  transition: 0.4s ease-in;

  &__container {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;

    color: var(--secundary-text-color);
    height: 100%;
    margin: 0 auto;
    padding: 1rem 0;
    width: 60%;
  }
}

@media (max-width: 1200px) {
  .header__container {
    min-width: 90%;
  }
}

@media (max-width: 992px) {
  .header {
    position: relative;

    &__container {
      justify-content: center;
      min-width: 100%;
    }
  }
}
</style>

