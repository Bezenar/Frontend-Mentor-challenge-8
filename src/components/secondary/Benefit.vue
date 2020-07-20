<template>
  <div class="wid-50">
    <div class="benefit__content">
      <div class="benefit__icon-wrapper">
        <img
          class="benefit__icon"
          :src="icon.src"
          :alt="icon.alt"
          :title="icon.title"
        />
      </div>
      <div class="benefit__heading-wrapper">
        <h3 class="benefit__heading">{{ heading }}</h3>
      </div>
      <div class="benefit__text-wrapper">
        <p class="benefit__text">{{ text }}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    icon: Object,
    heading: String,
    text: String
  }
};
</script>
<style lang="scss">
.benefit {
  &__content {
    text-align: center;
    color: $white;
    padding-top: 0.35rem;
    padding-bottom: 5rem;
  }
  &__heading {
    &-wrapper {
      padding: 1.65rem 0 0.65rem;
    }
    font-family: $secondFont;
    font-size: 19px;
    letter-spacing: 0.5px;
  }
  &__text {
    &-wrapper {
      padding: 0 5.75rem 0 4.25rem;
    }
    font-size: 14px;
    line-height: 20px;
  }
}
</style>
