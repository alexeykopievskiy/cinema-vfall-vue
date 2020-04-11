<template>
  <main class="v-fall-main v-fall-main--page-news">
    <div class="v-fall__container v-fall__container--white v-fall__container--main">
      <section class="v-fall-main-block grid grid-column">
        <h2 class="v-fall-main-block__header">Новости</h2>
        <div class="v-fall-main-block__container grid grid-wrap">
          <a
            href="#"
            @click.prevent="openNews(i)"
            v-for="i of 16"
            :key="i"
            class="v-fall-main-block__item v-fall-main-block__item--lg"
          >
            <img class="v-fall-main-block__img" src="~assets/img/img5.jpg" alt />
            <p
              class="v-fall-main-block__text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id</p>
          </a>
        </div>
        <button class="v-fall-main-block__btn btn btn-disabled" type="button">Загрузить еще</button>
      </section>
    </div>
  </main>
</template>

<script>
export default {
  methods: {
    openNews(i) {
      this.$router.push('/news/' + i)
    }
  }
};
</script>