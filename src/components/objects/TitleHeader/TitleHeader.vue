<template>
  <div class="header__box">
    <h1 class="header__title">Renata Marques</h1>
    <h2 class="header__subtitle">Front-End Developer</h2>
  </div>
</template>


<style lang="scss" scoped>
.header__title {
  color: var(--title-color-1);
  font-family: "Righteous", cursive;
  font-size: 1.8rem;
  font-weight: lighter;
  letter-spacing: 0.06rem;
  line-height: 2rem;
  margin: 0 0.5rem;
  text-align: center;
}

.header__subtitle {
  font-size: 1rem;
  font-weight: bolder;
  letter-spacing: 0.07rem;
  line-height: 1.8rem;
  margin: 0 0.5rem;
  text-align: center;
}

@media (max-width: 992px) {
  .header__box {
    display: flex;
    flex-direction: column;
    justify-content: center;

    height: 50%;
  }
}

@media (max-width: 576px) {
  .header__title {
    font-size: 1.6rem;
  }

  .header__subtitle {
    font-size: 1rem;
  }
}

@media (max-width: 330px) {
  .header__title {
    font-size: 1.4rem;
  }

  .header__subtitle {
    font-size: 0.8rem;
  }
}
</style>