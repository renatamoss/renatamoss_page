<template>
  <footer class="footer">
    <p>Personal WebSite RM © 2022</p>
    <div class="footer__line-second">
      <div>built with</div>
      <img
        class="image__footer-item"
        alt="Heart Image"
        src="@/../public/images/favicon-heart.png"
      />
      <div>Vue.Js</div>
      <img
        class="image__footer-item"
        alt="Vue Image"
        src="@/../public/images/favicon-vue.png"
      />
    </div>
  </footer>
</template>


<style lang="scss" scoped>
.footer {
  display: flex;
  align-items: center;
  justify-content: center;

  background-color: var(--bg-color-1);
  box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px,
    rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px,
    rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
  color: var(--secundary-text-color);
  font-size: var(--font-size-1);
  height: 100%;
  padding: 1rem 0;
  text-align: center;
  width: 100%;

  .image__footer-item {
    width: 1.5rem;
    padding: 0.3rem;
  }
  &__line-second {
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-left: 0.5rem;
  }
}

@media (max-width: 576px) {
  .footer {
    display: block;
    font-size: 0.8rem;
  }
}
</style>

