<template>
  <div class="small-card__wrapper">
    <div class="small-card__content">
      <p class="small-card__category monospace">{{ data.category }}</p>
      <p class="small-card__title">{{ data.title }}</p>
    </div>
    <div>
      <img class="small-card__image" :src="data.image" alt="sorry" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["data"],
};
</script>

<style lang="scss">
.small-card {
  &__wrapper {
    border-top: 0;
    display: flex;
    flex: 1 0 calc(50% - 0.5rem);
    flex-direction: column-reverse;
    justify-content: center;
    padding: 0 0 1rem;
    @media (min-width: 768px) {
      flex: 0;
      padding-bottom: 3rem;
      margin: 0;
    }
    @media (min-width: 1352px) {
      padding-left: 0;
      padding-right: 0;
    }
  }
  &__title {
    color: black;
    font-size: 1rem;
    letter-spacing: -0.04em;
    line-height: 1;
    text-align: right;
    text-transform: uppercase;
    overflow: hidden;
  }
  &__category {
    font-family: re;
    color: black;
    font-size: 0.7rem;
    margin: 1rem 0;
    text-transform: uppercase;
  }
  &__content {
    @media (max-width: 1025px) {
      width: 150px;
    }
    @media (max-width: 1025px) {
      width: 100%;
    }
  }
  &__image {
    @media (max-width: 1025px) {
      width: 150px;
    }
    @media (max-width: 1025px) {
      width: 100%;
    }
  }
}
</style>