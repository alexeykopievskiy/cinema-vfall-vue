<template>
  <form class="v-fall-header__search">
    <input class="v-fall-header__input" type="text" placeholder="Найти" />
  </form>
</template>

<style lang="scss">
.v-fall-header__search:before {
  content: url("~../assets/img/search.png");
  width: 16px;
  height: 16px;
  position: absolute;
  left: 21px;
  top: 13px;
  display: block;
  z-index: 1;
}
</style>