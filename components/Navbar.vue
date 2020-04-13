<template>
  <nav class="v-fall-header__nav" v-if="menu">
    <nuxt-link
      prefetch
      v-for="item in menu"
      :key="item.id"
      class="v-fall-header__link"
      :to="item.url"
    >{{item.name}}</nuxt-link>
  </nav>
</template>

<script>
export default {
  data: () => {
    return {
      menu: null
    };
  },
  mounted() {
    this.$axios.$get("https://api.videout.ru/source").then(response => {
      this.menu = response.toggleMenu;
    });
  }
};
</script>