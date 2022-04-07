<template>
  <div class="search__container">
    <input
      type="search"
      class="search__input"
      @input="onInput"
      placeholder="Pesquise aqui a tecnologia utilizada"
    />
  </div>
</template>


<script>
export default {
  methods: {
    onInput(text) {
      let search = text.target.value;
      this.$emit("searching", search);
    },
  },
};
</script>


<style lang="scss" scoped>
.search__container {
  padding-top: 0.5rem;
  margin: 0 auto;
  width: 60%;

  .search__input {
    border: 0.01rem solid var(--border-color);
    border-radius: 0.4rem;
    padding: 0.2rem 1rem;
    width: 100%;

    &::placeholder {
      opacity: 0.5;
    }
  }
}

@media (max-width: 1200px) {
  .search__container {
    width: 90%;
  }
}

@media (max-width: 992px) {
  .search__container {
    padding-left: 1rem;
    padding-right: 1rem;
    width: 100%;
  }
}
</style>