<template>
  <div class="button__back-home">
    <Button
      class="button__item button__item--back button__item--back-home"
      href="#home"
      title=""
      symbol="bi bi-arrow-up-circle-fill"
    />
  </div>
  <div class="button__back-header">
    <Button
      class="button__item button__item--back button__item--back-header"
      href="#header"
      title=""
      symbol="bi bi-arrow-up-circle-fill"
    />
  </div>
</template>
            
            
<script>
import Button from "@/components/shared/Button/Button.vue";

export default {
  components: {
    Button,
  },
};
</script>
            
            
<style lang="scss" scoped>
.button__back-home {
  display: flex;
  justify-content: right;

  bottom: 0;
  margin-right: 20%;
  padding-bottom: 4rem;
  position: fixed;
  right: 0;
  z-index: 1;
}

.button__back-header {
  display: none;
}

@media (max-width: 1200px) {
  .button__back-home {
    margin-right: 5%;
  }
}

@media (max-width: 992px) {
  .button__back-header {
    display: flex;
    justify-content: right;

    bottom: 0;
    margin-right: 1rem;
    padding-bottom: 4rem;
    position: fixed;
    right: 0;
    z-index: 1;
  }

  .button__back-home {
    display: none;
  }
}

@media (max-width: 576px) {
  .button__back-header {
    margin-right: 1rem;
    padding: 0.5rem 0 1.5rem 0;
    position: relative;
  }
}
</style>