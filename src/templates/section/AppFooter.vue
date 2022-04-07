<template>
  <footer class="footer">
    <div>Personal WebSite RM © 2022 | built with</div>
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
  </footer>
</template>


<style lang="scss" scoped>
.footer {
  display: flex;
  align-items: center;
  justify-content: center;

  background-color: var(--bg-color-3);
  color: var(--primary-text-color);
  font-size: var(--font-size-1);
  height: 100%;
  padding: 1rem 0;
  text-align: center;
  width: 100%;

  .image__footer-item {
    width: 1.5rem;
    padding: 0.3rem;
  }
}

@media (max-width: 430px) {
  .footer {
    font-size: 0.7rem;
  }
}
</style>

