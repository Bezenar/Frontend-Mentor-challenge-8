<template>
  <div class="nav-wrapper">
    <ul class="nav">
      <li class="nav-item" v-for="item in navItem" :key="item.id">
        <a :href="item.link"> {{ item.text }} </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ColumnNav",
  props: {
    navItem: Array
  }
};
</script>

<style lang="scss" scoped></style>
