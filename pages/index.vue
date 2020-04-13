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
    <!--<div class="v-fall-main-slide__controls">
      <button class="v-fall-main-slide__prev"></button>
      <button class="v-fall-main-slide__next"></button>
    </div>-->
    <div
      class="v-fall__container v-fall__container--white v-fall__container--main"
      style="padding-top: 10px; margin-top: 10px;"
    >
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Новинки</h2>
        <div class="v-fall-main-block__container" v-if="hot">
          <a
            @click.prevent="openVideo(item.url)"
            v-for="item in hot.slice(0, 6)"
            :key="item.id"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <h3 class="v-fall-main-block__title">{{item.title}}</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">{{item.year}}</span>
              <span class="v-fall-main-block__elem">{{item.category[0]}}</span>
            </p>
          </a>
        </div>
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Фильмы</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container" v-if="films">
          <a
            @click.prevent="openVideo(item.url)"
            v-for="item in films.slice(0, 6)"
            :key="item.id"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <h3 class="v-fall-main-block__title">{{item.title}}</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">{{item.year}}</span>
              <span class="v-fall-main-block__elem">{{item.category[0]}}</span>
            </p>
          </a>
        </div>
      </section>
      <!--<section class="v-fall-main-block v-fall-main-block__carousel">
      <h2 class="v-fall-main-block__header">Planeta online</h2>-->
      <!--<no-ssr>
        <carousel
          class="v-fall-main-block__container v-fall-main-block__container-carousel"
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
        </carousel>
      </no-ssr>-->
      <!--<div class="v-fall-main-block__carousel-btn">
          <button class="v-fall-main-block__carousel-left"></button>
          <button class="v-fall-main-block__carousel-right"></button>
        </div>
      </section>-->
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Мультфильмы</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container" v-if="cartoons">
          <a
            @click.prevent="openVideo(item.url)"
            v-for="item in cartoons.slice(0, 6)"
            :key="item.id"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <h3 class="v-fall-main-block__title">{{item.title}}</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">{{item.year}}</span>
              <span class="v-fall-main-block__elem">{{item.category}}</span>
            </p>
          </a>
        </div>
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Новости</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container" v-if="news">
          <a
            @click.prevent="openNews(item.url)"
            v-for="item of news.slice(0, 4)"
            :key="item.id"
            class="v-fall-main-block__item v-fall-main-block__item--lg"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <p
              class="v-fall-main-block__text"
            >{{item.title}}</p>
          </a>
        </div>
      </section>
    </div>
  </main>
</template>

<script>
//import carousel from 'vue-owl-carousel'
let requestNew = 'https://api.videout.ru/search/?genre=0&year=2019&country=0&sorting=rate'
let requestFilms = 'https://api.videout.ru/search/'
let requestCartoons = 'https://api.videout.ru/search/?genre=73'
let requestNews = 'https://api.videout.ru/news'

export default {
  data: () => {
    return {
      source: null,
      hot: null,
      films: null,
      cartoons: null,
      news: null
    };
  },
  methods: {
    openVideo(i) {
      this.$router.push(i);
    },
    openNews(i) {
      this.$router.push(i);
    }
  },
  async asyncData({$axios, params}) {
    let responseNew = await $axios.get(requestNew)
    let responseFilms = await $axios.get(requestFilms)
    let responeCartoons = await $axios.get(requestCartoons)
    let responseNews = await $axios.get(requestNews)
    return {
      hot: responseNew.data.data,
      films: responseFilms.data.data,
      cartoons: responeCartoons.data.data,
      news: responseNews.data.data
    }
  }
};
</script>

<style lang="scss">
.v-fall-main {
  &-slide {
    &__prev {
      margin-left: 80px;
      background: transparent url("../assets/img/arrow.png") no-repeat;
      width: 27px;
      height: 42px;
      border: none;
      outline: none;
      cursor: pointer;

      &:hover {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        transform: rotate(-180deg);
      }
    }
    &__next {
      margin-right: 80px;
      margin-left: 80px;
      background: transparent url("../assets/img/arrow.png") no-repeat;
      width: 27px;
      height: 42px;
      border: none;
      outline: none;
      transform: rotate(-180deg);
      cursor: pointer;

      &:hover {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        transform: rotate(0deg);
      }
    }
  }
  &-block {
    &__carousel {
      &-left {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        width: 27px;
        height: 42px;
        margin-left: 24px;
        transform: rotate(-180deg);
        border: none;
        outline: none;
        cursor: pointer;
        position: relative;
        z-index: 100;
      }
      &-right {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        width: 27px;
        height: 42px;
        margin-right: 24px;
        border: none;
        outline: none;
        cursor: pointer;
        position: relative;
        z-index: 100;
      }
    }
  }
}
</style>
