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
    transition: 0.2s ease-in;
  }

  .image__default--home {
    border-radius: 400px;
    background: url("../../../../public/images/fundo-stars.jpeg");
    background-size: cover;
    background-position: center;
    /* box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px; */
    padding: 3rem;
    width: 100%;
  }

  .image__default--photo-renata {
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
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
  .image__default--home {
    max-width: 60%;
    padding: 2rem !important;
  }

  .image__default--photo-renata {
    margin: 1rem 0 3rem 0;
    max-width: 80%;
  }
}

@media (max-width: 576px) {
  .image__default--photo-renata {
    margin-bottom: 0;
  }
}
</style>