<template>
  <h3 class="banner__text">{{ bannerText }}</h3>
</template>

<script>
export default {
  data: () => {
    return {
      bannerText: "",
      bannerPhrase:
        "Olá! Eu sou Renata e seja bem-vindo(a) ao meu Portfólio!",
      bannerSpeed: 100,
      charIndex: 0,
    };
  },
  methods: {
    showBanner() {
      this.bannerText += this.bannerPhrase.charAt(this.charIndex);
      this.charIndex += 1;
      setTimeout(this.showBanner, this.bannerSpeed);
    },
  },
  created() {
    this.showBanner();
  },
};
</script>


<style lang="scss" scoped>
.banner__text {
  color: var(--title-color-6);
  font-family: "Righteous", cursive;
  font-size: 1.6rem;
  font-weight: lighter;
  height: 100px;
  letter-spacing: 0.06rem;
  line-height: 2rem;
  width: 260px;
}

@media (max-width: 576px) {
  .banner__text {
    font-size: 1.4rem;
    line-height: 1.3;
  }
}

/*max-height*/
@media screen and (max-height: 700px) {
  .banner__text {
    font-size: 1.2rem;
  }
}
</style>
