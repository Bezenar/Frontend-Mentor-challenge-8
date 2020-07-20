<template>
  <div class="line-wrapper">
    <div class="flex">
      <div class="line__icon-wrapper">
        <img
          class="line__icon"
          :src="icon.src"
          :alt="icon.alt"
          :title="icon.title"
        />
      </div>
      <div class="line__text-wrapper">
        <div class="line__text">
          {{ text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactLine",
  props: {
    icon: Object,
    text: String
  }
};
</script>

<style lang="scss">
.line {
  &__icon {
    &-wrapper {
    }
  }
  &__text {
    &-wrapper {
    }
  }
}
</style>