<template>
  <main class="v-fall-main v-fall-main--page-list">
    <div class="v-fall__container v-fall__container--white v-fall__container--list">
      <section class="v-fall-main-block grid grid-column">
        <h2 class="v-fall-main-block__header">Новинки</h2>
        <div class="v-fall-main-block__container grid grid-wrap">
          <a
            @click.prevent="openVideo(i)"
            v-for="i of 18"
            :key="i"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" src="~assets/img/img1.jpg" alt />
            <h3 class="v-fall-main-block__title">Фаворитка</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">2011</span>
              <span class="v-fall-main-block__elem">Мелодрамма</span>
            </p>
          </a>
        </div>
        <button class="v-fall-main-block__btn btn btn-default" type="button">Загрузить еще</button>
      </section>
    </div>
  </main>
</template>

<script>
export default {
  methods: {
    openVideo(i) {
      this.$router.push("/video/" + i);
    }
  }
};
</script>