<template>
  <div class="logo-wrapper">
    <a :href="logo.link">
      <img :src="logo.src" :alt="logo.alt" :title="logo.title" />
    </a>
  </div>
</template>

<script>
export default {
  name: "Logo",
  data() {
    return {
      logo: {
        link: "logo-link",
        src: "./images/logo.svg",
        alt: "Logo",
        title: "Fylo"
      }
    };
  }
};
</script>
<style lang="scss"></style>
