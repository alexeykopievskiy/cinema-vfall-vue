<template>
  <main class="v-fall-main">
    <!--<section class="v-fall-main-slider owl-carousel">
      <div class="v-fall-main-slide">
        <img src="~assets/img/slide1.jpg" alt />
        <div class="v-fall-main-slide__content">
          <p class="v-fall-main-slide__label">
            <span class="v-fall-main-slide__text">2019</span>
            <span class="v-fall-main-slide__text">Мелодрамма</span>
          </p>
          <h3 class="v-fall-main-slide__title">Фаворитка</h3>
        </div>
      </div>
      <div class="v-fall-main-slide">
        <img src="~assets/img/slide1.jpg" alt />
        <div class="v-fall-main-slide__content">
          <p class="v-fall-main-slide__label">
            <span class="v-fall-main-slide__text">2019</span>
            <span class="v-fall-main-slide__text">Мелодрамма</span>
          </p>
          <h3 class="v-fall-main-slide__title">Фаворитка</h3>
        </div>
      </div>
      <div class="v-fall-main-slide">
        <img src="~assets/img/slide1.jpg" alt />
        <div class="v-fall-main-slide__content">
          <p class="v-fall-main-slide__label">
            <span class="v-fall-main-slide__text">2019</span>
            <span class="v-fall-main-slide__text">Мелодрамма</span>
          </p>
          <h3 class="v-fall-main-slide__title">Фаворитка</h3>
        </div>
      </div>
      <div class="v-fall-main-slide">
        <img src="~assets/img/slide1.jpg" alt />
        <div class="v-fall-main-slide__content">
          <p class="v-fall-main-slide__label">
            <span class="v-fall-main-slide__text">2019</span>
            <span class="v-fall-main-slide__text">Мелодрамма</span>
          </p>
          <h3 class="v-fall-main-slide__title">Фаворитка</h3>
        </div>
      </div>
    </section>-->
    <div class="v-fall-main-slide__controls">
      <button class="v-fall-main-slide__prev"></button>
      <button class="v-fall-main-slide__next"></button>
    </div>
    <div class="v-fall__container v-fall__container--white v-fall__container--main">
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Новинки</h2>
        <div class="v-fall-main-block__container">
          <a
            @click.prevent="openVideo(i)"
            v-for="i of 6"
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
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Фильмы</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container">
          <a
            @click.prevent="openVideo(i)"
            v-for="i of 6"
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
      </section>
      <section class="v-fall-main-block v-fall-main-block__carousel">
        <h2 class="v-fall-main-block__header">Planeta online</h2>
        <div
          class="v-fall-main-block__container v-fall-main-block__container-carousel owl-carousel"
        >
          <a
            @click.prevent="openVideo(i)"
            v-for="i of 4"
            :key="i"
            class="v-fall-main-block__item v-fall-main-block__item--lg"
            href="#"
          >
            <img class="v-fall-main-block__img" src="~assets/img/img5.jpg" alt />
            <h3 class="v-fall-main-block__title">Фаворитка</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">2011</span>
              <span class="v-fall-main-block__elem">Мелодрамма</span>
            </p>
          </a>
        </div>
        <div class="v-fall-main-block__carousel-btn">
          <button class="v-fall-main-block__carousel-left"></button>
          <button class="v-fall-main-block__carousel-right"></button>
        </div>
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Мультфильмы</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container">
          <a
            @click.prevent="openVideo(i)"
            v-for="i of 6"
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
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Новости</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container">
          <a
            @click.prevent="openNews(i)"
            v-for="i of 4"
            :key="i"
            class="v-fall-main-block__item v-fall-main-block__item--lg"
            href="#"
          >
            <img class="v-fall-main-block__img" src="~assets/img/img5.jpg" alt />
            <p
              class="v-fall-main-block__text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id</p>
          </a>
        </div>
      </section>
    </div>
  </main>
</template>

<script>
export default {
  methods: {
    openVideo(i) {
      this.$router.push("/video/" + i)
    },
    openNews(i) {
      this.$router.push("/news/" + i)
    }
  }
};
</script>

<style>
</style>
