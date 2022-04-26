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

  .image__default--home-study {
    width: 100%;
  }

  .image__default--photo-renata {
    box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px,
      rgba(0, 0, 0, 0.3) 0px 7px 13px -3px,
      rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
    width: 100%;
  }

  .image__default--vertical {
    height: auto;
  }

  .image__default--banner-page {
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    width: 100%;
  }
}

@media (min-width: 992px) {
  .image__default:hover {
    transform: scale(1.03);
  }
}

@media (max-width: 992px) {
  .image__default--home-study {
    max-width: 70%;
  }

  .image__default--photo-renata {
    margin: 1rem 0 4rem 0;
    max-width: 80%;
  }
}

</style>