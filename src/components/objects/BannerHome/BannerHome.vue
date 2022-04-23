<template>
  <h3 class="banner__text">{{ bannerText }}</h3>
</template>


<script>
export default {
  data: () => {
    return {
      bannerText: "",
      bannerPhrase:
        "Olá! Meu nome é Renata e seja bem-vindo(a) ao meu Portfólio!",
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
  font-size: var(--font-size-3);
  font-weight: lighter;
  height: 100px;
  letter-spacing: 0.06rem;
  line-height: 2rem;
  max-width: 360px;
}

@media (max-width: 992px) {
  .banner__text {
    font-size: var(--font-size-2);
    height: 64px;
  }
}
@media (max-width: 576px) {
  .banner__text {
    font-size: 1.2rem;
    line-height: 1.3;
    /* max-width: 300px; */
  }
}
</style>
