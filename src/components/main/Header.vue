<template>
  <header id="header">
    <div class="container">
      <div class="flex jc-sb ai-center">
        <Logo></Logo>
        <nav>
          <ul class="flex nav_wrapper">
            <li class="nav__item" v-for="item in links" :key="item.id">
              <a :href="item.href">{{ item.title }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
import Logo from "../secondary/Logo";
export default {
  name: "Header",
  components: { Logo },
  data() {
    return {
      links: [
        {
          id: "1",
          title: "Features",
          href: "Features"
        },
        {
          id: "2",
          title: "Team",
          href: "Team"
        },
        {
          id: "3",
          title: "Sign In",
          href: "Sign In"
        }
      ]
    };
  }
};
</script>
<style lang="scss">
#header {
  background-color: $darkBlue-introBg;
  padding: 4.5rem 0 1rem;
  .nav {
    &__item {
      font-size: 17px;
      font-family: $secondFont;
      padding-left: 3.5rem;
      a {
        color: $white;
      }
      &:hover {
        transition: all 0.3s linear;
        transform: scale(1.3);
      }
    }
  }
}
</style>
