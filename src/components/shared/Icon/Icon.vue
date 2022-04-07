<template>
  <svg class="icon">
    <use :xlink:href="`${require('@/assets/icons.svg')}#${$props.symbol}`" />
  </svg>
</template>


<script>
export default {
  props: {
    symbol: String,
  },
};
</script>


<style lang="scss" scoped>
.icon {
  fill: var(--color-link);
  font-weight: bolder;
  height: 1.2rem;
  margin: 0.5rem;
  width: 1.2rem;
}
</style>