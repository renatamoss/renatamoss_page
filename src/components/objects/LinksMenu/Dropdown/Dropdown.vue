<template>
  <div class="dropdown">
    <!--button toggle  -->
    <button class="dropdown__button" href="#" @click.prevent="toggleDropdown()">
      <label class="toggle__menu">
        <ul>
          <li></li>
          <li></li>
          <li></li>
        </ul>
      </label>
    </button>

    <!--container float -->
    <transition name="fade-links">
      <LinksList
        class="social__box--dropdown"
        v-show="isOpen"
        @closeDropdown="closeDropdown"
      />
    </transition>
  </div>
</template>
            
            
<script>
import LinksList from "@/components/objects/LinksMenu/LinksList/LinksList.vue";

export default {
  components: {
    LinksList,
  },

  data() {
    return {
      isOpen: false,
    };
  },

  methods: {
    toggleDropdown() {
      this.isOpen = !this.isOpen;
    },

    closeDropdown() {
      this.isOpen = false;
    },

    clickOutListener(evt) {
      if (!this.$el.contains(evt.target)) {
        this.closeDropdown();
      }
    },
    handleScroll() {
      if (this.isOpen) {
        this.closeDropdown();
      }
    },
  },

  mounted() {
    document.addEventListener("click", this.clickOutListener);
    document.addEventListener("scroll", this.handleScroll);
  },
  //Disconnect addEventListiner
  beforeUnmount() {
    document.removeEventListener("click", this.clickOutListener);
    document.removeEventListener("scroll", this.handleScroll);
  },
};
</script>
                
            
<style lang="scss" scoped>
.dropdown {
  display: none;
}

@media (max-width: 992px) {
  .dropdown {
    display: block;
    height: 50%;
    padding-left: 1rem;
    position: relative;
    width: 3.75rem;

    &__button {
      display: flex;
      align-items: center;
      justify-content: center;

      background-color: var(--bg-color-1);
      cursor: pointer;
      height: 100%;
      width: 100%;
      z-index: 1;

      .toggle__menu ul {
        width: 1.8rem;
      }

      .toggle__menu ul li {
        background-color: var(--color-link);
        height: 0.2rem;
        margin-bottom: 0.3rem;
        width: 100%;
      }

      .toggle__menu ul li:last-child {
        margin-bottom: 0px;
      }
    }
  }
}

@keyframes links-come-down {
  0% {
    opacity: 0;
    transform: translateY(-8rem);
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.fade-links-enter,
.fade-links-enter-active {
  animation: links-come-down 0.6s;
}

.fade-links-leave-to {
  transition: all 0.2s ease-out;
  opacity: 0;
}
</style>

