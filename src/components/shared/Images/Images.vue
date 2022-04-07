<template>
  <div class="image__box">
    <img
      :class="className"
      :src="require(`../../../../public/images/${fileName}`)"
      :alt="descriptionImage"
    />
  </div>
</template>


<script>
export default {
  props: {
    className: {
      type: [String, Array],
    },
    fileName: {
      type: String,
    },
    descriptionImage: {
      type: String,
    },
  },
};
</script>


<style lang="scss" scoped>
.image__box {
  display: flex;
  justify-content: center;

  .image__default {
    border-radius: 0.4rem;
    height: auto;
    width: 100%;
    transition: all 0.1s linear;
  }

  .image__default--home-woman {
    width: 100%;
  }

  .image__default--home-study {
    padding-top: 1rem;
    width: 50%;
  }

  .image__default--vertical {
    height: auto;
  }

  .image__default--banner-page {
        box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px,
      rgba(60, 64, 67, 0.15) 0px 2px 6px 2px;
    width: 60%;
  }
}

@media (min-width: 992px) {
  .image__default:hover {
    transform: scale(1.03);
  }
}

@media (max-width: 1200px) {
   .image__default--banner-page {
    min-width: 90%;
  }
}

@media (max-width: 992px) {
  .image__default--home-woman {
    max-width: 70%;
  }

   .image__default--banner-page {
    min-width: 100%;
  }
}
</style>