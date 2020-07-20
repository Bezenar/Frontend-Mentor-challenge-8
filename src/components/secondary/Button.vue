<template>
  <div class="button-wrapper">
    <a :href="link">
      <button class="button button_rounded button_cyan-blue">{{ name }}</button>
    </a>
  </div>
</template>
<script>
export default {
  name: "Button",
  props: {
    name: String,
    link: String
  }
};
</script>
<style lang="scss">
.button {
  color: $white;
  padding: 1.1rem 6rem;
  font-size: 17px;
  cursor: pointer;
  &-wrapper {
    padding: 1.95rem 0;
  }
  &_rounded {
    border-radius: 30px;
  }
  &_cyan-blue {
    background: linear-gradient($cyan, $blue);
    &:hover {
      transition: all 0.3s linear;
      background: linear-gradient(45deg, $darkBlue-mainBg, $blue);
      color: $darkBlue-mainBg;
    }
  }
}
</style>
