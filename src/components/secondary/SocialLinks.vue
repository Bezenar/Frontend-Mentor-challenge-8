<template>
  <div class="flex wrap">
    <div class="socialLink-wrapper" v-for="item in socialLinks" :key="item.id">
      <a class="socialLink__link" :href="item.href">
        <img
          class="socialLink__icon"
          :src="item.icon.src"
          :alt="item.icon.alt"
          :title="item.icon.title"
        />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "SocailLinks",
  data() {
    return {
      socialLinks: [
        {
          id: 1,
          icon: {
            src: "./images/icon-facebook.svg",
            alt: "Facebook",
            title: "Facebook"
          },
          link: "Facebook"
        },
        {
          id: 2,
          icon: {
            src: "./images/icon-twitter.svg",
            alt: "Twitter",
            title: "Twitter"
          },
          link: "Twitter"
        },
        {
          id: 3,
          icon: {
            src: "./images/icon-instagram.svg",
            alt: "Instagram",
            title: "Instagram"
          },
          link: "Instagram"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped></style>
